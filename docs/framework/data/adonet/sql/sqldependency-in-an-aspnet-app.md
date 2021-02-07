---
description: '자세히 알아보기: ASP.NET 응용 프로그램의 SqlDependency'
title: ASP.NET 애플리케이션에서 SqlDependency
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ff226ce3-f6b5-47a1-8d22-dc78b67e07f5
ms.openlocfilehash: 686586af834884f97ff8e62fdc792b3cdc23f507
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99767026"
---
# <a name="sqldependency-in-an-aspnet-application"></a>ASP.NET 애플리케이션에서 SqlDependency

이 섹션의 예제는 ASP.NET <xref:System.Web.Caching.SqlCacheDependency> 개체를 활용하여 <xref:System.Data.SqlClient.SqlDependency>를 간접적으로 사용하는 방법을 보여 줍니다. <xref:System.Web.Caching.SqlCacheDependency> 개체는 <xref:System.Data.SqlClient.SqlDependency>를 사용하여 알림을 수신하고 캐시를 올바르게 업데이트합니다.  
  
> [!NOTE]
> 이 샘플 코드에서는 [쿼리 알림을 사용 하도록 설정](enabling-query-notifications.md)하는 스크립트를 실행 하 여 쿼리 알림을 사용 하도록 설정 했다고 가정 합니다.  
  
## <a name="about-the-sample-application"></a>샘플 애플리케이션 정보  

 애플리케이션 예제에서는 단일 ASP.NET 웹 페이지를 사용하여 **AdventureWorks** SQL Server 데이터베이스의 제품 정보를 <xref:System.Web.UI.WebControls.GridView> 컨트롤에 표시합니다. 페이지가 로드되면 코드는 <xref:System.Web.UI.WebControls.Label> 컨트롤에 현재 시간을 씁니다. 그런 다음 <xref:System.Web.Caching.SqlCacheDependency> 개체를 정의하고 최대 3분 동안 캐시 데이터를 저장하도록 <xref:System.Web.Caching.Cache> 개체의 속성을 설정합니다. 그런 다음 코드는 데이터베이스에 연결하고 데이터를 검색합니다. 페이지가 로드되고 애플리케이션이 실행 중인 경우 ASP.NET은 캐시에서 데이터를 검색하여 페이지의 시간이 변경되지 않는다는 것을 확인할 수 있습니다. 모니터링되는 데이터가 변경되면 ASP.NET은 캐시를 무효화하고 `GridView` 컨트롤을 새로운 데이터로 다시 채우고 `Label` 컨트롤에 표시되는 시간을 업데이트합니다.  
  
## <a name="creating-the-sample-application"></a>샘플 애플리케이션 만들기  

 샘플 애플리케이션을 만들고 실행하려면 다음 단계를 따릅니다.  
  
1. 새 ASP.NET 웹 사이트 만들기  
  
2. Default.aspx 페이지에 <xref:System.Web.UI.WebControls.Label> 및 <xref:System.Web.UI.WebControls.GridView> 컨트롤을 추가합니다.  
  
3. 페이지의 클래스 모듈을 열고 다음 지시문을 추가합니다.  
  
    ```vb  
    Option Strict On  
    Option Explicit On  
  
    Imports System.Data.SqlClient  
    ```  
  
    ```csharp  
    using System.Data.SqlClient;  
    using System.Web.Caching;  
    ```  
  
4. 페이지의 `Page_Load` 이벤트에 다음 코드를 추가합니다.  
  
     [!code-csharp[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#1)]
     [!code-vb[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#1)]  
  
5. `GetConnectionString` 및 `GetSQL`의 두 가지 도우미 메서드를 추가합니다. 정의된 연결 문자열은 통합 보안을 사용합니다. 사용 중인 계정에 필요한 데이터베이스 권한이 있는지, 그리고 **AdventureWorks** 샘플 데이터베이스에서 알림을 사용했는지를 확인해야 합니다.
  
     [!code-csharp[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#2)]
     [!code-vb[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#2)]  
  
### <a name="testing-the-application"></a>애플리케이션 테스트  

 애플리케이션은 웹 양식에 표시된 데이터를 캐시하고 활동이 없으면 3분마다 새로 고칩니다. 데이터베이스가 변경되면 즉시 캐시를 새로 고칩니다. Visual Studio에서 애플리케이션을 실행합니다. 그러면 페이지가 브라우저에 로드됩니다. 표시된 캐시 새로 고침 시간은 캐시를 마지막으로 새로 고친 시간을 나타냅니다. 3분간 기다렸다가 페이지를 새로 고쳐 다시 게시 이벤트를 발생시킵니다. 페이지에 표시된 시간이 변경되었습니다. 3분 이내에 페이지를 새로 고치면 페이지에 표시되는 시간이 동일하게 유지됩니다.  
  
 이제 Transact-SQL UPDATE 명령을 사용하여 데이터베이스의 데이터를 업데이트하고 페이지를 새로 고칩니다. 이제 표시된 시간은 캐시가 데이터베이스의 새 데이터로 새로 고쳐졌음을 나타냅니다. 캐시를 업데이트하는 경우에도 페이지에 표시되는 시간은 포스트백 이벤트가 발생할 때까지 변경되지 않습니다.  

## <a name="distributed-cache-synchronization-using-sql-dependency"></a>SQL 종속성을 사용한 분산 캐시 동기화

[NCache](https://www.alachisoft.com/ncache) 와 같은 일부 타사 분산 캐시는 sql [종속성](https://www.alachisoft.com/resources/docs/ncache/prog-guide/sql-dependency.html)을 사용 하 여 sql database 및 캐시를 동기화 할 수 있도록 지원 합니다. 소스 코드 구현에 대 한 자세한 내용 및 예제는 [Distributed CACHE SQL 종속성 샘플](https://github.com/Alachisoft/NCache-Samples/tree/master/dotnet/Dependencies/SQLDependency)을 참조 하세요.

## <a name="see-also"></a>참고 항목

- [SQL Server의 쿼리 알림](query-notifications-in-sql-server.md)
- [ADO.NET 개요](../ado-net-overview.md)
