---
description: '자세한 정보: 저장소 확장성'
title: 저장소 확장성
ms.date: 03/30/2017
ms.assetid: 7c3f4a46-4bac-4138-ae6a-a7c7ee0d28f5
ms.openlocfilehash: f04c466224aacd1c8f755e7aa60b18846d0c7180
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755228"
---
# <a name="store-extensibility"></a>저장소 확장성

<xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>를 사용하면 사용자가 지속성 데이터베이스의 인스턴스를 쿼리하는 데 사용할 수 있는 애플리케이션별 사용자 지정 속성을 승격할 수 있습니다. 속성을 승격하면 값을 데이터베이스의 특수 뷰 내에서 사용할 수 있습니다. 사용자 쿼리에 사용할 수 있는 이러한 승격된 속성은 단순 형식(예: Guid, String, DateTime 등)이거나 serialize된 이진 형식(byte[])일 수 있습니다.

<xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> 클래스에는 속성을 쿼리에서 사용할 수 있는 속성으로 승격시키는 데 사용할 수 있는 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.Promote%2A> 메서드가 있습니다. 다음은 스토리지 확장에 대한 엔드투엔드 예제입니다.

1. 이 예제 시나리오에서 DP(문서 처리) 애플리케이션에는 문서 처리를 위해 사용자 지정 활동을 사용하는 워크플로가 있습니다. 이러한 워크플로에는 최종 사용자에게 표시되어야 하는 상태 변수 집합이 있습니다. 이를 위해 DP 애플리케이션은 활동에서 상태 변수를 제공하는 데 사용되는 <xref:System.Activities.Persistence.PersistenceParticipant> 형식의 인스턴스 확장을 제공합니다.

    ```csharp
    class DocumentStatusExtension : PersistenceParticipant
    {
        public string DocumentId;
        public string ApprovalStatus;
        public string UserName;
        public DateTime LastUpdateTime;
    }
    ```

2. 그러면 호스트에 새 확장이 추가됩니다.

    ```csharp
    static Activity workflow = CreateWorkflow();
    WorkflowApplication application = new WorkflowApplication(workflow);
    DocumentStatusExtension documentStatusExtension = new DocumentStatusExtension ();
    application.Extensions.Add(documentStatusExtension);
    ```

     사용자 지정 지 속성 참가자를 추가 하는 방법에 대 한 자세한 내용은 [지 속성 참가자](persistence-participants.md) 샘플을 참조 하세요.

3. DP 응용 프로그램의 사용자 지정 활동은 **Execute** 메서드의 다양 한 상태 필드를 채웁니다.

    ```csharp
    public override void Execute(CodeActivityContext context)
    {
        // ...
        context.GetExtension<DocumentStatusExtension>().DocumentId = Guid.NewGuid();
        context.GetExtension<DocumentStatusExtension>().UserName = "John Smith";
        context.GetExtension<DocumentStatusExtension>().ApprovalStatus = "Approved";
        context.GetExtension<DocumentStatusExtension>().LastUpdateTime = DateTime.Now();
        // ...
    }
    ```

4. 워크플로 인스턴스가 지 속성 지점에 도달 하면 **Documentstatusextension** 지 속성 참가자의 **CollectValues** 메서드는 이러한 속성을 지 속성 데이터 컬렉션에 저장 합니다.

    ```csharp
    class DocumentStatusExtension : PersistenceParticipant
    {
        const XNamespace xNS = XNamespace.Get("http://contoso.com/DocumentStatus");

        protected override void CollectValues(out IDictionary<XName, object> readWriteValues, out IDictionary<XName, object> writeOnlyValues)
        {
            readWriteValues = new Dictionary<XName, object>();
            readWriteValues.Add(xNS.GetName("UserName"), this.UserName);
            readWriteValues.Add(xNS.GetName("ApprovalStatus"), this.ApprovalStatus);
            readWriteValues.Add(xNS.GetName("DocumentId"), this.DocumentId);
            readWriteValues.Add(xNS.GetName("LastModifiedTime"), this.LastUpdateTime);

            writeOnlyValues = null;
        }
        // ...
    }
    ```

    > [!NOTE]
    > 이러한 모든 속성은 지 속성 프레임 워크에서 **SaveWorkflowCommand 데이터** 컬렉션을 통해 **SqlWorkflowInstanceStore** 에 전달 됩니다.

5. DP 응용 프로그램은 SQL 워크플로 인스턴스 저장소를 초기화 하 고 **promote** 메서드를 호출 하 여이 데이터를 승격 합니다.

    ```csharp
    SqlWorkflowInstanceStore store = new SqlWorkflowInstanceStore(connectionString);

    List<XName> variantProperties = new List<XName>()
    {
        xNS.GetName("UserName"),
        xNS.GetName("ApprovalStatus"),
        xNS.GetName("DocumentId"),
        xNS.GetName("LastModifiedTime")
    };

    store.Promote("DocumentStatus", variantProperties, null);
    ```

    이 승격 정보를 기반으로 **SqlWorkflowInstanceStore** 는 [InstancePromotedProperties](#InstancePromotedProperties) 뷰의 열에 데이터 속성을 배치 합니다.

6. 승격 테이블에서 데이터 하위 집합을 쿼리하기 위해 DP 애플리케이션은 승격 뷰의 맨 위에 사용자 지정된 뷰를 추가합니다.

    ```sql
    create view [dbo].[DocumentStatus] with schemabinding
    as
        select  P.[InstanceId] as [InstanceId],
            P.Value1 as [UserName],
            P.Value2 as [ApprovalStatus],
            P.Value3 as [DocumentId],
            P.Value4 as [LastUpdatedTime]
    from [System.Activities.DurableInstancing].[InstancePromotedProperties] as P
    where P.PromotionName = N'DocumentStatus'
    go
    ```

## <a name="systemactivitiesdurableinstancinginstancepromotedproperties-view"></a><a name="InstancePromotedProperties"></a> [DurableInstancing InstancePromotedProperties] 뷰

|열 이름|열 유형|설명|
|-----------------|-----------------|-----------------|
|InstanceId|GUID|이 승격이 속하는 워크플로 인스턴스입니다.|
|PromotionName|nvarchar(400)|승격 자체의 이름입니다.|
|Value1, Value2, Value3,..,Value32|sql_variant|승격된 속성 자체의 값입니다. 길이가 8000바이트를 초과하는 이진 BLOB와 문자열을 제외한 대부분의 SQL 기본 데이터 형식이 sql_variant에 저장될 수 있습니다.|
|Value33, Value34, Value35, …, Value64|varbinary(max)|varbinary(max)로 명시적으로 선언되는 승격된 속성의 값입니다.|
