---
title: 활동 라이브러리
ms.date: 03/30/2017
ms.assetid: 5323e9d4-71d6-47eb-bfa6-31feac62044d
ms.openlocfilehash: fae2a94b5e5e776625aa7f26700980640b66afd4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142903"
---
# <a name="activity-library"></a>활동 라이브러리
이 섹션에는 WF(Windows 워크플로파)의 고급 사용자 지정 활동을 보여 주는 샘플이 포함되어 있습니다.  
  
## <a name="in-this-section"></a>섹션 내용

 [SendMail 사용자 지정 작업](sendmail-custom-activity.md)  
 워크플로 애플리케이션 내에서 사용하기 위해 <xref:System.Activities.AsyncCodeActivity>로부터 파생되는 사용자 지정 활동을 만들어 SMTP를 사용하여 메일을 보내는 방법을 보여 줍니다.  
  
 [Throttled Parallel ForEach](throttled-parallel-foreach.md)  
 `ThrottleParallelForEach` 활동이 실행할 동시 분기 수를 제한하는 동시 비율을 설정하도록 허용한다는 점만 제외하고 <xref:System.Activities.Statements.ParallelForEach%601> 활동과 어떻게 비슷한지를 보여 줍니다.
  
 [데이터베이스 액세스 작업](database-access-activities.md)  
 데이터베이스에 액세스하는 것이 정보를 검색 또는 수정하고 [ADO.NET](../../data/adonet/index.md) 사용하여 데이터베이스에 액세스할 수 있도록 하는 활동을 만드는 방법을 보여 줍니다.  
  
 [.NET Framework 4.5의 구체화된 정책 작업](externalized-policy-activity-in-net-framework-4-5.md)  
 외부화된Policy4 활동을 통해 WF 3.5에 제공된 규칙 엔진을 사용하여 WF 4.5(WF 4.5)의 Windows 워크플로 파운데이션에서 .NET Framework 3.5(WF 3.5) <xref:System.Workflow.Activities.Rules.RuleSet> 개체에서 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] 기존 Windows 워크플로 파운데이션을 직접 실행하는 방법을 보여 줍니다.
  
 [제네릭이 아닌 ForEach](non-generic-foreach.md)  
 비제네릭 버전의 <xref:System.Activities.Statements.ForEach%601> 활동을 만드는 방법을 보여 줍니다.  
  
 [제네릭이 아닌 ParallelForEach](non-generic-parallelforeach.md)  
 비제네릭 버전의 <xref:System.Activities.Statements.ParallelForEach%601> 활동을 만드는 방법을 보여 줍니다.  
  
 [WorkflowInstanceId 가져오기](get-workflowinstanceid.md)  
 사용자 지정 활동인 `GetWorkflowInstanceId`를 사용하여 워크플로 인스턴스 ID를 반환하는 방법을 보여 줍니다.
