---
title: '방법: WorkflowServiceHost를 사용하여 워크플로의 처리되지 않은 예외 동작 구성'
ms.date: 03/30/2017
ms.assetid: 51b25c86-292c-43e4-8d13-273d2badc8ad
ms.openlocfilehash: 8f7fe203a4198aa98e8aee1be3a12e4d72a066f8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175411"
---
# <a name="how-to-configure-workflow-unhandled-exception-behavior-with-workflowservicehost"></a><span data-ttu-id="061b5-102">방법: WorkflowServiceHost를 사용하여 워크플로의 처리되지 않은 예외 동작 구성</span><span class="sxs-lookup"><span data-stu-id="061b5-102">How to: Configure Workflow Unhandled Exception Behavior with WorkflowServiceHost</span></span>
<span data-ttu-id="061b5-103"><xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>는 <xref:System.ServiceModel.Activities.WorkflowServiceHost>에서 호스팅되는 워크플로 내에서 처리되지 않은 예외가 발생할 경우 수행할 작업을 지정할 수 있도록 하는 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="061b5-103">The <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> is a behavior that enables you to specify the action to take if an unhandled exception occurs within a workflow hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="061b5-104">이 항목에서는 구성 파일에서 이 동작을 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="061b5-104">This topic shows how to configure this behavior in a configuration file.</span></span>  
  
### <a name="to-configure-workflowunhandledexceptionbehavior"></a><span data-ttu-id="061b5-105">WorkflowUnhandledExceptionBehavior를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="061b5-105">To configure WorkflowUnhandledExceptionBehavior</span></span>  
  
1.  <span data-ttu-id="061b5-106">추가 <`workflowUnhandledException`> 요소에는 <`behavior`> 내의 요소를 <`serviceBehaviors`> 요소를 사용 하 여를 `action` 다음 예와에서 같이 처리 되지 않은 예외가 발생할 경우 수행할 동작을 지정 하는 특성.</span><span class="sxs-lookup"><span data-stu-id="061b5-106">Add a <`workflowUnhandledException`> element in a <`behavior`> element within a <`serviceBehaviors`> element, using the `action` attribute to specify the action to take when an unhandled exception occurs as shown in the following example.</span></span>  
  
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
    >  <span data-ttu-id="061b5-107">위의 샘플에서 사용하는 구성은 단순화된 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="061b5-107">The preceding configuration sample is using simplified configuration.</span></span> <span data-ttu-id="061b5-108">자세한 내용은 [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="061b5-108">For more information, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md).</span></span>  
  
     <span data-ttu-id="061b5-109">이 동작은 다음 예제와 같이 코드에서 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="061b5-109">This behavior can be configured in code as shown in the following example.</span></span>  
  
    ```csharp  
    host.Description.Behaviors.Add(new WorkflowUnhandledExceptionBehavior { Action = WorkflowUnhandledExceptionAction.AbandonAndSuspend });  
    ```  
  
     <span data-ttu-id="061b5-110">`action` 특성을 <`workflowUnhandledException`> 요소는 다음 값 중 하나로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="061b5-110">The `action` attribute of the <`workflowUnhandledException`> element can be set to one of the following values:</span></span>  
  
     **<span data-ttu-id="061b5-111">abandon</span><span class="sxs-lookup"><span data-stu-id="061b5-111">abandon</span></span>**  
     <span data-ttu-id="061b5-112">유지되는 인스턴스 상태를 변경하지 않고 메모리에서 인스턴스를 중단합니다. 즉, 마지막 유지 지점으로 롤백합니다.</span><span class="sxs-lookup"><span data-stu-id="061b5-112">Aborts the instance in memory without touching the persisted instance state (that is, roll back to the last persist point).</span></span>  
  
     **<span data-ttu-id="061b5-113">abandonAndSuspend</span><span class="sxs-lookup"><span data-stu-id="061b5-113">abandonAndSuspend</span></span>**  
     <span data-ttu-id="061b5-114">메모리에서 인스턴스를 중단하고 유지되는 인스턴스가 일시 중단되도록 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="061b5-114">Aborts the instance in memory and updates the persisted instance to be suspended.</span></span>  
  
     **<span data-ttu-id="061b5-115">cancel</span><span class="sxs-lookup"><span data-stu-id="061b5-115">cancel</span></span>**  
     <span data-ttu-id="061b5-116">인스턴스에 대한 취소 처리기를 호출하고 메모리에서 인스턴스를 완료합니다. 이 경우 인스턴스가 인스턴스 저장소에서 제거될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="061b5-116">Calls cancellation handlers for the instance and then completes the instance in memory, which may also remove it from the instance store</span></span>  
  
     **<span data-ttu-id="061b5-117">terminate</span><span class="sxs-lookup"><span data-stu-id="061b5-117">terminate</span></span>**  
     <span data-ttu-id="061b5-118">메모리에서 인스턴스를 완료하고 인스턴스 저장소에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="061b5-118">Completes the instance in memory and removes it from the instance store.</span></span>  
  
     <span data-ttu-id="061b5-119">에 대 한 자세한 내용은 <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>를 참조 하세요 [워크플로 서비스 호스트 확장성](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="061b5-119">For more information about <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>, see [Workflow Service Host Extensibility](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="061b5-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="061b5-120">See also</span></span>

- [<span data-ttu-id="061b5-121">워크플로 서비스 호스트 확장</span><span class="sxs-lookup"><span data-stu-id="061b5-121">Workflow Service Host Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)
- [<span data-ttu-id="061b5-122">워크플로 서비스</span><span class="sxs-lookup"><span data-stu-id="061b5-122">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
