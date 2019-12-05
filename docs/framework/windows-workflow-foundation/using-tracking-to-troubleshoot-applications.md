---
title: 추적을 사용하여 애플리케이션 문제 해결
ms.date: 03/30/2017
ms.assetid: 8851adde-c3c2-4391-9523-d8eb831490af
ms.openlocfilehash: b07e850810734082568ddca9776a72575c986094
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837560"
---
# <a name="using-tracking-to-troubleshoot-applications"></a><span data-ttu-id="e59ec-102">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="e59ec-102">Using Tracking to Troubleshoot Applications</span></span>
<span data-ttu-id="e59ec-103">WF (Windows Workflow Foundation)를 사용 하면 워크플로 관련 정보를 추적 하 여 Windows Workflow Foundation 응용 프로그램 또는 서비스의 실행에 대 한 세부 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e59ec-103">Windows Workflow Foundation (WF) enables you to track workflow-related information to give details into the execution of a Windows Workflow Foundation application or service.</span></span> <span data-ttu-id="e59ec-104">Windows Workflow Foundation 호스트는 워크플로 인스턴스를 실행 하는 동안 워크플로 이벤트를 캡처할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e59ec-104">Windows Workflow Foundation hosts are able to capture workflow events during the execution of a workflow instance.</span></span> <span data-ttu-id="e59ec-105">워크플로에서 오류 또는 예외를 생성 하는 경우 Windows Workflow Foundation 추적 정보를 사용 하 여 처리 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e59ec-105">If your workflow generates faults or exceptions, you can use the Windows Workflow Foundation tracking details to troubleshooting its processing.</span></span>  
  
## <a name="troubleshooting-a-wf-using-wf-tracking"></a><span data-ttu-id="e59ec-106">WF 추적을 사용한 WF 문제 해결</span><span class="sxs-lookup"><span data-stu-id="e59ec-106">Troubleshooting a WF using WF Tracking</span></span>  
 <span data-ttu-id="e59ec-107">Windows Workflow Foundation 활동을 처리 하는 동안 오류를 감지 하려면 오류가 발생 한 <xref:System.Activities.Tracking.ActivityStateRecord>를 쿼리 하는 추적 프로필을 사용 하 여 추적을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e59ec-107">To detect faults within the processing of a Windows Workflow Foundation activity, you can enable tracking with a tracking profile that queries for an <xref:System.Activities.Tracking.ActivityStateRecord> with the state of Faulted.</span></span> <span data-ttu-id="e59ec-108">해당 쿼리는 다음 코드로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e59ec-108">The corresponding query is specified in the following code.</span></span>  
  
```xml  
<activityStateQueries>  
              <activityStateQuery activityName="*">  
                <states>  
                  <state name="Faulted" />  
                </states>  
              </activityStateQuery>  
 </activityStateQueries>  
```  
  
 <span data-ttu-id="e59ec-109">오류가 전파되어 오류 처리기(예: <xref:System.Activities.Statements.TryCatch> 활동) 내에서 처리되면 <xref:System.Activities.Tracking.FaultPropagationRecord>를 사용하여 오류를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e59ec-109">If a fault is propagated and handled within a fault handler (such as a <xref:System.Activities.Statements.TryCatch> activity) this can be detected using a <xref:System.Activities.Tracking.FaultPropagationRecord>.</span></span> <span data-ttu-id="e59ec-110"><xref:System.Activities.Tracking.FaultPropagationRecord>는 오류의 소스 활동과 오류 처리기의 이름을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e59ec-110">The <xref:System.Activities.Tracking.FaultPropagationRecord> indicates the source activity of the fault and the name of the fault handler.</span></span> <span data-ttu-id="e59ec-111"><xref:System.Activities.Tracking.FaultPropagationRecord> 오류에 대 한 예외 스택의 형태로 오류 세부 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e59ec-111">The <xref:System.Activities.Tracking.FaultPropagationRecord> contains fault details in form of the exception stack for the fault.</span></span> <span data-ttu-id="e59ec-112"><xref:System.Activities.Tracking.FaultPropagationRecord>를 구독 하는 쿼리는 다음 예제에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e59ec-112">The query to subscribe for a <xref:System.Activities.Tracking.FaultPropagationRecord> is shown in the following example.</span></span>  
  
```xml  
<faultPropagationQueries>  
              <faultPropagationQuery faultSourceActivityName ="*" faultHandlerActivityName="*"/>  
 </faultPropagationQueries>  
```  
  
 <span data-ttu-id="e59ec-113">오류가 워크플로 내에서 처리되지 않으면 워크플로 인스턴스에서 처리되지 않은 예외가 발생하고 워크플로 인스턴스가 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="e59ec-113">If a fault is not handled within the workflow it results in an unhandled exception at the workflow instance and the workflow instance is aborted.</span></span> <span data-ttu-id="e59ec-114">처리되지 않은 예외의 세부 정보를 이해하려면 다음 예제에 지정된 대로 추적 프로필에서 `state name="UnhandledException"`인 워크플로 인스턴스 레코드를 쿼리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e59ec-114">To understand the details of the unhandled exception, the tracking profile must query the workflow instance record with `state name="UnhandledException"` as specified in the following example.</span></span>  
  
```xml  
<workflowInstanceQueries>  
              <workflowInstanceQuery>  
                <states>  
                  <state name="UnhandledException" />  
                </states>  
              </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
 <span data-ttu-id="e59ec-115">워크플로 인스턴스가 처리 되지 않은 예외를 발견 하면 Windows Workflow Foundation 추적을 사용 하도록 설정한 경우 <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord> 개체를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="e59ec-115">When a workflow instance encounters an unhandled exception, a <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord> object is emitted if Windows Workflow Foundation tracking has been enabled.</span></span>  
  
 <span data-ttu-id="e59ec-116">이 추적 레코드에는 예외 스택의 형태로 오류 세부 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e59ec-116">This tracking record contains the fault details in the form of the exception stack.</span></span> <span data-ttu-id="e59ec-117">오류가 발생 하 여 처리 되지 않은 예외를 발생 시킨 오류 (예: 활동)의 원본에 대 한 세부 정보를 포함 합니다. Windows Workflow Foundation에서 오류 이벤트를 구독 하려면 추적 참가자를 추가 하 여 추적을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e59ec-117">It has details of the source of the fault (for example, the activity) that faulted and resulted in the unhandled exception.To subscribe to fault events from a Windows Workflow Foundation, enable tracking by adding a tracking participant.</span></span> <span data-ttu-id="e59ec-118">이 참가자는 `ActivityStateQuery (state="Faulted")`, <xref:System.Activities.Tracking.FaultPropagationRecord> 및 `WorkflowInstanceQuery (state="UnhandledException")`를 쿼리하는 추적 프로필을 사용하여 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e59ec-118">Configure this participant with a tracking profile that queries for `ActivityStateQuery (state="Faulted")`, <xref:System.Activities.Tracking.FaultPropagationRecord>, and `WorkflowInstanceQuery (state="UnhandledException")`.</span></span>  
  
 <span data-ttu-id="e59ec-119">ETW 추적 참가자를 사용하여 추적을 활성화하면 오류 이벤트가 ETW 세션으로 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="e59ec-119">If tracking is enabled using the ETW tracking participant, the fault events are emitted to an ETW session.</span></span> <span data-ttu-id="e59ec-120">Event Viewer 이벤트 뷰어를 사용하여 이벤트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e59ec-120">The events can be viewed using the Event Viewer event viewer.</span></span> <span data-ttu-id="e59ec-121">이는 분석 채널의 노드 **이벤트 뷰어-> 응용 프로그램 및 서비스 로그-> Microsoft > Windows > 응용 프로그램 서버** 에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e59ec-121">This can be found under the node **Event Viewer->Applications and Services Logs->Microsoft->Windows->Application Server-Applications** in the analytic channel.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e59ec-122">참조</span><span class="sxs-lookup"><span data-stu-id="e59ec-122">See also</span></span>

- <span data-ttu-id="e59ec-123">[Windows Server App Fabric 모니터링](https://docs.microsoft.com/previous-versions/appfabric/ee677251(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="e59ec-123">[Windows Server App Fabric Monitoring](https://docs.microsoft.com/previous-versions/appfabric/ee677251(v=azure.10))</span></span>
- <span data-ttu-id="e59ec-124">[App Fabric을 사용 하 여 응용 프로그램 모니터링](https://docs.microsoft.com/previous-versions/appfabric/ee677276(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="e59ec-124">[Monitoring Applications with App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677276(v=azure.10))</span></span>
