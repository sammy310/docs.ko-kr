---
title: <bufferReceive>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b23c3a54-10d4-4f13-ab6d-98b26b76f22a
ms.openlocfilehash: 360d26fda964fa33640e833ad22dab7e06e153f6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59203160"
---
# <a name="bufferreceive"></a><span data-ttu-id="4ca73-101">\<bufferReceive></span><span class="sxs-lookup"><span data-stu-id="4ca73-101">\<bufferReceive></span></span>
<span data-ttu-id="4ca73-102">서비스에서 버퍼링되는 수신 처리를 사용할 수 있도록 하는 서비스 동작입니다. 이를 통해 워크플로 서비스가 순서가 맞지 않는 메시지를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ca73-102">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
<span data-ttu-id="4ca73-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="4ca73-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="4ca73-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="4ca73-104">\<behaviors></span></span>  
<span data-ttu-id="4ca73-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="4ca73-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="4ca73-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="4ca73-106">\<behavior></span></span>  
<span data-ttu-id="4ca73-107">\<bufferReceive></span><span class="sxs-lookup"><span data-stu-id="4ca73-107">\<bufferReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ca73-108">구문</span><span class="sxs-lookup"><span data-stu-id="4ca73-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4ca73-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4ca73-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4ca73-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca73-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4ca73-111">특성</span><span class="sxs-lookup"><span data-stu-id="4ca73-111">Attributes</span></span>  
  
|<span data-ttu-id="4ca73-112">특성</span><span class="sxs-lookup"><span data-stu-id="4ca73-112">Attribute</span></span>|<span data-ttu-id="4ca73-113">설명</span><span class="sxs-lookup"><span data-stu-id="4ca73-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4ca73-114">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="4ca73-114">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="4ca73-115">각 채널에 허용되는 최대 보류 메시지 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="4ca73-115">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="4ca73-116">기본값은 512입니다.</span><span class="sxs-lookup"><span data-stu-id="4ca73-116">The default value is 512.</span></span> <span data-ttu-id="4ca73-117">이 속성은 워크플로 서비스가 수신할 수 있는 순서가 맞지 않는 메시지의 수를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca73-117">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4ca73-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4ca73-118">Child Elements</span></span>  
 <span data-ttu-id="4ca73-119">없음</span><span class="sxs-lookup"><span data-stu-id="4ca73-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4ca73-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4ca73-120">Parent Elements</span></span>  
  
|<span data-ttu-id="4ca73-121">요소</span><span class="sxs-lookup"><span data-stu-id="4ca73-121">Element</span></span>|<span data-ttu-id="4ca73-122">설명</span><span class="sxs-lookup"><span data-stu-id="4ca73-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4ca73-123">\<동작 >의 \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="4ca73-123">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="4ca73-124">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca73-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4ca73-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="4ca73-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.BufferedReceiveServiceBehavior>
- <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>
