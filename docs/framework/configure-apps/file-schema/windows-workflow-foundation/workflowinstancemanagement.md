---
title: <workflowInstanceManagement>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
ms.openlocfilehash: 98bc1b24da6e65a11a39d133057c1bb55b003a58
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61613463"
---
# <a name="workflowinstancemanagement"></a><span data-ttu-id="0804e-101">\<workflowInstanceManagement></span><span class="sxs-lookup"><span data-stu-id="0804e-101">\<workflowInstanceManagement></span></span>
<span data-ttu-id="0804e-102">지속성 예외, 처리되지 않은 예외 동작 및 유휴 동작을 비롯하여 워크플로 인스턴스 실행 방법을 제어하는 설정을 지정할 수 있는 서비스 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="0804e-102">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
<span data-ttu-id="0804e-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0804e-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="0804e-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="0804e-104">\<behaviors></span></span>  
<span data-ttu-id="0804e-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="0804e-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="0804e-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="0804e-106">\<behavior></span></span>  
<span data-ttu-id="0804e-107">\<workflowInstanceManagement></span><span class="sxs-lookup"><span data-stu-id="0804e-107">\<workflowInstanceManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0804e-108">구문</span><span class="sxs-lookup"><span data-stu-id="0804e-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0804e-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0804e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="0804e-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0804e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0804e-111">특성</span><span class="sxs-lookup"><span data-stu-id="0804e-111">Attributes</span></span>  
  
|<span data-ttu-id="0804e-112">특성</span><span class="sxs-lookup"><span data-stu-id="0804e-112">Attribute</span></span>|<span data-ttu-id="0804e-113">설명</span><span class="sxs-lookup"><span data-stu-id="0804e-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0804e-114">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="0804e-114">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="0804e-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0804e-115">Child Elements</span></span>  
 <span data-ttu-id="0804e-116">없음</span><span class="sxs-lookup"><span data-stu-id="0804e-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0804e-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0804e-117">Parent Elements</span></span>  
  
|<span data-ttu-id="0804e-118">요소</span><span class="sxs-lookup"><span data-stu-id="0804e-118">Element</span></span>|<span data-ttu-id="0804e-119">설명</span><span class="sxs-lookup"><span data-stu-id="0804e-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0804e-120">\<동작 >의 \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="0804e-120">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="0804e-121">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0804e-121">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0804e-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="0804e-122">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>
