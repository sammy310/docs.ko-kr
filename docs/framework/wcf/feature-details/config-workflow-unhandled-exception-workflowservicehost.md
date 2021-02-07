---
description: '자세히 알아보기: 방법: WorkflowServiceHost를 사용 하 여 워크플로 처리 되지 않은 예외 동작 구성'
title: '방법: WorkflowServiceHost를 사용하여 워크플로의 처리되지 않은 예외 동작 구성'
ms.date: 03/30/2017
ms.assetid: 51b25c86-292c-43e4-8d13-273d2badc8ad
ms.openlocfilehash: 7d32ccf1262895d948cae26f0922adf3003664ba
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99743384"
---
# <a name="how-to-configure-workflow-unhandled-exception-behavior-with-workflowservicehost"></a><span data-ttu-id="21109-103">방법: WorkflowServiceHost를 사용하여 워크플로의 처리되지 않은 예외 동작 구성</span><span class="sxs-lookup"><span data-stu-id="21109-103">How to: Configure Workflow Unhandled Exception Behavior with WorkflowServiceHost</span></span>

<span data-ttu-id="21109-104"><xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>는 <xref:System.ServiceModel.Activities.WorkflowServiceHost>에서 호스팅되는 워크플로 내에서 처리되지 않은 예외가 발생할 경우 수행할 작업을 지정할 수 있도록 하는 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="21109-104">The <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> is a behavior that enables you to specify the action to take if an unhandled exception occurs within a workflow hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="21109-105">이 항목에서는 구성 파일에서 이 동작을 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="21109-105">This topic shows how to configure this behavior in a configuration file.</span></span>  
  
### <a name="to-configure-workflowunhandledexceptionbehavior"></a><span data-ttu-id="21109-106">WorkflowUnhandledExceptionBehavior를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="21109-106">To configure WorkflowUnhandledExceptionBehavior</span></span>  
  
1. <span data-ttu-id="21109-107">`workflowUnhandledException` `behavior` `serviceBehaviors` `action` 다음 예제와 같이 처리 되지 않은 예외가 발생할 때 수행할 작업을 지정 하는 특성을 사용 하 여 <> 요소 내의 <> 요소에 <> 요소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="21109-107">Add a <`workflowUnhandledException`> element in a <`behavior`> element within a <`serviceBehaviors`> element, using the `action` attribute to specify the action to take when an unhandled exception occurs as shown in the following example.</span></span>  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <workflowUnhandledException action="abandonAndSuspend"/>
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="21109-108">위의 샘플에서 사용하는 구성은 단순화된 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="21109-108">The preceding configuration sample is using simplified configuration.</span></span> <span data-ttu-id="21109-109">자세한 내용은 [간소화 된 구성](../simplified-configuration.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="21109-109">For more information, see [Simplified Configuration](../simplified-configuration.md).</span></span>  
  
     <span data-ttu-id="21109-110">이 동작은 다음 예제와 같이 코드에서 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21109-110">This behavior can be configured in code as shown in the following example.</span></span>  
  
    ```csharp  
    host.Description.Behaviors.Add(new WorkflowUnhandledExceptionBehavior { Action = WorkflowUnhandledExceptionAction.AbandonAndSuspend });  
    ```  
  
     <span data-ttu-id="21109-111">`action`<> 요소의 특성은 `workflowUnhandledException` 다음 값 중 하나로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21109-111">The `action` attribute of the <`workflowUnhandledException`> element can be set to one of the following values:</span></span>  
  
     <span data-ttu-id="21109-112">**제거할**</span><span class="sxs-lookup"><span data-stu-id="21109-112">**abandon**</span></span>  
     <span data-ttu-id="21109-113">유지되는 인스턴스 상태를 변경하지 않고 메모리에서 인스턴스를 중단합니다. 즉, 마지막 유지 지점으로 롤백합니다.</span><span class="sxs-lookup"><span data-stu-id="21109-113">Aborts the instance in memory without touching the persisted instance state (that is, roll back to the last persist point).</span></span>  
  
     <span data-ttu-id="21109-114">**abandonAndSuspend**</span><span class="sxs-lookup"><span data-stu-id="21109-114">**abandonAndSuspend**</span></span>  
     <span data-ttu-id="21109-115">메모리에서 인스턴스를 중단하고 유지되는 인스턴스가 일시 중단되도록 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="21109-115">Aborts the instance in memory and updates the persisted instance to be suspended.</span></span>  
  
     <span data-ttu-id="21109-116">**cancel**</span><span class="sxs-lookup"><span data-stu-id="21109-116">**cancel**</span></span>  
     <span data-ttu-id="21109-117">인스턴스에 대한 취소 처리기를 호출하고 메모리에서 인스턴스를 완료합니다. 이 경우 인스턴스가 인스턴스 저장소에서 제거될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21109-117">Calls cancellation handlers for the instance and then completes the instance in memory, which may also remove it from the instance store</span></span>  
  
     <span data-ttu-id="21109-118">**끝나야**</span><span class="sxs-lookup"><span data-stu-id="21109-118">**terminate**</span></span>  
     <span data-ttu-id="21109-119">메모리에서 인스턴스를 완료하고 인스턴스 저장소에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="21109-119">Completes the instance in memory and removes it from the instance store.</span></span>  
  
     <span data-ttu-id="21109-120">에 대 한 자세한 내용은 <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> [워크플로 서비스 호스트 확장성](workflow-service-host-extensibility.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="21109-120">For more information about <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>, see [Workflow Service Host Extensibility](workflow-service-host-extensibility.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21109-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="21109-121">See also</span></span>

- [<span data-ttu-id="21109-122">워크플로 서비스 호스트 확장</span><span class="sxs-lookup"><span data-stu-id="21109-122">Workflow Service Host Extensibility</span></span>](workflow-service-host-extensibility.md)
- [<span data-ttu-id="21109-123">워크플로 서비스</span><span class="sxs-lookup"><span data-stu-id="21109-123">Workflow Services</span></span>](workflow-services.md)
