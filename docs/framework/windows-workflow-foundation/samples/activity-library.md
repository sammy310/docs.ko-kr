---
title: 활동 라이브러리
ms.date: 03/30/2017
ms.assetid: 5323e9d4-71d6-47eb-bfa6-31feac62044d
ms.openlocfilehash: b701d382c25644181b23f3c0f0cd8e019b8d37d1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61909183"
---
# <a name="activity-library"></a><span data-ttu-id="42d42-102">활동 라이브러리</span><span class="sxs-lookup"><span data-stu-id="42d42-102">Activity Library</span></span>
<span data-ttu-id="42d42-103">이 섹션에는 고급 사용자 지정 활동에서 Windows WF (Workflow Foundation)를 보여 주는 샘플이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42d42-103">This section contains samples that demonstrate advanced custom activities in Windows Workflow Foundation (WF).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="42d42-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="42d42-104">In This Section</span></span>

 [<span data-ttu-id="42d42-105">SendMail 사용자 지정 작업</span><span class="sxs-lookup"><span data-stu-id="42d42-105">SendMail Custom Activity</span></span>](sendmail-custom-activity.md)  
 <span data-ttu-id="42d42-106">워크플로 응용 프로그램 내에서 사용하기 위해 <xref:System.Activities.AsyncCodeActivity>로부터 파생되는 사용자 지정 활동을 만들어 SMTP를 사용하여 메일을 보내는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="42d42-106">Demonstrates how to create a custom activity that derives from <xref:System.Activities.AsyncCodeActivity> to send mail using SMTP for use within a workflow application.</span></span>  
  
 [<span data-ttu-id="42d42-107">Throttled Parallel ForEach</span><span class="sxs-lookup"><span data-stu-id="42d42-107">Throttled Parallel ForEach</span></span>](throttled-parallel-foreach.md)  
 <span data-ttu-id="42d42-108">`ThrottleParallelForEach` 활동이 실행할 동시 분기 수를 제한하는 동시 비율을 설정하도록 허용한다는 점만 제외하고 <xref:System.Activities.Statements.ParallelForEach%601> 활동과 어떻게 비슷한지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="42d42-108">Demonstrates how the `ThrottleParallelForEach` activity is similar to the <xref:System.Activities.Statements.ParallelForEach%601> activity with the one exception that it allows setting a concurrency factor to restrict the number of simultaneous branches to execute.</span></span>
  
 [<span data-ttu-id="42d42-109">데이터베이스 액세스 작업</span><span class="sxs-lookup"><span data-stu-id="42d42-109">Database Access Activities</span></span>](database-access-activities.md)  
 <span data-ttu-id="42d42-110">검색 하거나 정보를 수정 하 고 사용 하 여 데이터베이스에 액세스할 수 있도록 활동을 만드는 방법을 보여 줍니다 [ADO.NET](https://go.microsoft.com/fwlink/?LinkId=166081) 데이터베이스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42d42-110">Demonstrates how to create activities that allow accessing databases to retrieve or modify information and use [ADO.NET](https://go.microsoft.com/fwlink/?LinkId=166081) to access the database.</span></span>  
  
 [<span data-ttu-id="42d42-111">.NET Framework 4.5의 구체화된 정책 작업</span><span class="sxs-lookup"><span data-stu-id="42d42-111">Externalized Policy Activity in .NET Framework 4.5</span></span>](externalized-policy-activity-in-net-framework-4-5.md)  
 <span data-ttu-id="42d42-112">ExternalizedPolicy4 활동을 통해 기존 Windows Workflow Foundation을 실행 하는 방법을 보여 줍니다 [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF 3.5) <xref:System.Workflow.Activities.Rules.RuleSet> 개체에서 Windows Workflow Foundation의 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF 4.5) 직접 사용 하 여 규칙 엔진 즉 WF 3.5에서 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="42d42-112">Demonstrates how the ExternalizedPolicy4 activity allows executing existing Windows Workflow Foundation in [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF 3.5) <xref:System.Workflow.Activities.Rules.RuleSet> objects in Windows Workflow Foundation in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF 4.5) directly by using the rules engine that is shipped in WF 3.5.</span></span> 
  
 [<span data-ttu-id="42d42-113">제네릭이 아닌 ForEach</span><span class="sxs-lookup"><span data-stu-id="42d42-113">Non-Generic ForEach</span></span>](non-generic-foreach.md)  
 <span data-ttu-id="42d42-114">비제네릭 버전의 <xref:System.Activities.Statements.ForEach%601> 활동을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="42d42-114">Demonstrates how to create a non-generic version of the <xref:System.Activities.Statements.ForEach%601> activity.</span></span>  
  
 [<span data-ttu-id="42d42-115">제네릭이 아닌 ParallelForEach</span><span class="sxs-lookup"><span data-stu-id="42d42-115">Non-Generic ParallelForEach</span></span>](non-generic-parallelforeach.md)  
 <span data-ttu-id="42d42-116">비제네릭 버전의 <xref:System.Activities.Statements.ParallelForEach%601> 활동을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="42d42-116">Demonstrates how to create a non-generic version of the <xref:System.Activities.Statements.ParallelForEach%601> activity.</span></span>  
  
 [<span data-ttu-id="42d42-117">WorkflowInstanceId 가져오기</span><span class="sxs-lookup"><span data-stu-id="42d42-117">Get WorkflowInstanceId</span></span>](get-workflowinstanceid.md)  
 <span data-ttu-id="42d42-118">사용자 지정 활동인 `GetWorkflowInstanceId`를 사용하여 워크플로 인스턴스 ID를 반환하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="42d42-118">Demonstrates how to use the custom activity, `GetWorkflowInstanceId`, to return the workflow instance ID.</span></span>
