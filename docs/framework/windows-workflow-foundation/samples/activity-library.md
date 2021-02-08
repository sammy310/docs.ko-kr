---
description: 작업 라이브러리에 대해 자세히 알아보세요.
title: 활동 라이브러리
ms.date: 03/30/2017
ms.assetid: 5323e9d4-71d6-47eb-bfa6-31feac62044d
ms.openlocfilehash: 7e59846d34b63683266fed2c4ec1ad4ed5cb9566
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792611"
---
# <a name="activity-library"></a><span data-ttu-id="b6794-103">활동 라이브러리</span><span class="sxs-lookup"><span data-stu-id="b6794-103">Activity Library</span></span>

<span data-ttu-id="b6794-104">이 섹션에는 WF (Windows Workflow Foundation)의 고급 사용자 지정 작업을 보여 주는 샘플이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6794-104">This section contains samples that demonstrate advanced custom activities in Windows Workflow Foundation (WF).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b6794-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="b6794-105">In This Section</span></span>

 [<span data-ttu-id="b6794-106">SendMail 사용자 지정 활동</span><span class="sxs-lookup"><span data-stu-id="b6794-106">SendMail Custom Activity</span></span>](sendmail-custom-activity.md)  
 <span data-ttu-id="b6794-107">워크플로 애플리케이션 내에서 사용하기 위해 <xref:System.Activities.AsyncCodeActivity>로부터 파생되는 사용자 지정 활동을 만들어 SMTP를 사용하여 메일을 보내는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b6794-107">Demonstrates how to create a custom activity that derives from <xref:System.Activities.AsyncCodeActivity> to send mail using SMTP for use within a workflow application.</span></span>  
  
 [<span data-ttu-id="b6794-108">Throttled Parallel ForEach</span><span class="sxs-lookup"><span data-stu-id="b6794-108">Throttled Parallel ForEach</span></span>](throttled-parallel-foreach.md)  
 <span data-ttu-id="b6794-109">`ThrottleParallelForEach` 활동이 실행할 동시 분기 수를 제한하는 동시 비율을 설정하도록 허용한다는 점만 제외하고 <xref:System.Activities.Statements.ParallelForEach%601> 활동과 어떻게 비슷한지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b6794-109">Demonstrates how the `ThrottleParallelForEach` activity is similar to the <xref:System.Activities.Statements.ParallelForEach%601> activity with the one exception that it allows setting a concurrency factor to restrict the number of simultaneous branches to execute.</span></span>
  
 [<span data-ttu-id="b6794-110">Database Access Activities</span><span class="sxs-lookup"><span data-stu-id="b6794-110">Database Access Activities</span></span>](database-access-activities.md)  
 <span data-ttu-id="b6794-111">데이터베이스에 액세스 하 여 정보를 검색 하거나 수정 하 고 [ADO.NET](../../data/adonet/index.md) 를 사용 하 여 데이터베이스에 액세스할 수 있도록 하는 활동을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b6794-111">Demonstrates how to create activities that allow accessing databases to retrieve or modify information and use [ADO.NET](../../data/adonet/index.md) to access the database.</span></span>  
  
 [<span data-ttu-id="b6794-112">.NET Framework 4.5의 구체화된 정책 작업</span><span class="sxs-lookup"><span data-stu-id="b6794-112">Externalized Policy Activity in .NET Framework 4.5</span></span>](externalized-policy-activity-in-net-framework-4-5.md)  
 <span data-ttu-id="b6794-113">ExternalizedPolicy4 활동을 통해 wf <xref:System.Workflow.Activities.Rules.RuleSet> [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] 3.5에서 제공 되는 규칙 엔진을 사용 하 여 (wf 4.5)의 Windows Workflow Foundation에서 .NET Framework 3.5 (wf 3.5) 개체의 기존 Windows Workflow Foundation를 실행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b6794-113">Demonstrates how the ExternalizedPolicy4 activity allows executing existing Windows Workflow Foundation in .NET Framework 3.5 (WF 3.5) <xref:System.Workflow.Activities.Rules.RuleSet> objects in Windows Workflow Foundation in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF 4.5) directly by using the rules engine that is shipped in WF 3.5.</span></span>
  
 [<span data-ttu-id="b6794-114">비제네릭 ForEach</span><span class="sxs-lookup"><span data-stu-id="b6794-114">Non-Generic ForEach</span></span>](non-generic-foreach.md)  
 <span data-ttu-id="b6794-115">비제네릭 버전의 <xref:System.Activities.Statements.ForEach%601> 활동을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b6794-115">Demonstrates how to create a non-generic version of the <xref:System.Activities.Statements.ForEach%601> activity.</span></span>  
  
 [<span data-ttu-id="b6794-116">제네릭이 아닌 ParallelForEach</span><span class="sxs-lookup"><span data-stu-id="b6794-116">Non-Generic ParallelForEach</span></span>](non-generic-parallelforeach.md)  
 <span data-ttu-id="b6794-117">비제네릭 버전의 <xref:System.Activities.Statements.ParallelForEach%601> 활동을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b6794-117">Demonstrates how to create a non-generic version of the <xref:System.Activities.Statements.ParallelForEach%601> activity.</span></span>  
  
 [<span data-ttu-id="b6794-118">WorkflowInstanceId 가져오기</span><span class="sxs-lookup"><span data-stu-id="b6794-118">Get WorkflowInstanceId</span></span>](get-workflowinstanceid.md)  
 <span data-ttu-id="b6794-119">사용자 지정 활동인 `GetWorkflowInstanceId`를 사용하여 워크플로 인스턴스 ID를 반환하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b6794-119">Demonstrates how to use the custom activity, `GetWorkflowInstanceId`, to return the workflow instance ID.</span></span>
