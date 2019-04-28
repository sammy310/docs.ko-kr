---
title: <synchronousReceive> 요소
ms.date: 03/30/2017
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
ms.openlocfilehash: 20390f747c8beaccba1cfea7a9ea0ed366037ecb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757926"
---
# <a name="synchronousreceive-element"></a><span data-ttu-id="e007e-102">\<synchronousReceive > 요소</span><span class="sxs-lookup"><span data-stu-id="e007e-102">\<synchronousReceive> element</span></span>
<span data-ttu-id="e007e-103">이 구성 요소는 서비스 또는 클라이언트 응용 프로그램에서 메시지 수신을 위한 런타임 동작을 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e007e-103">This configuration element is used to specify run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="e007e-104">이 구성 요소에는 특성이나 자식 요소가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e007e-104">It does not have any attributes or child elements.</span></span>  
  
 <span data-ttu-id="e007e-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e007e-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="e007e-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="e007e-106">\<behaviors></span></span>  
<span data-ttu-id="e007e-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="e007e-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="e007e-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="e007e-108">\<behavior></span></span>  
<span data-ttu-id="e007e-109">\<synchronousReceive></span><span class="sxs-lookup"><span data-stu-id="e007e-109">\<synchronousReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e007e-110">구문</span><span class="sxs-lookup"><span data-stu-id="e007e-110">Syntax</span></span>  
  
```xml  
<synchronousReceive />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e007e-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e007e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e007e-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e007e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e007e-113">특성</span><span class="sxs-lookup"><span data-stu-id="e007e-113">Attributes</span></span>  
 <span data-ttu-id="e007e-114">없음</span><span class="sxs-lookup"><span data-stu-id="e007e-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e007e-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e007e-115">Child Elements</span></span>  
 <span data-ttu-id="e007e-116">없음</span><span class="sxs-lookup"><span data-stu-id="e007e-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e007e-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e007e-117">Parent Elements</span></span>  
  
|<span data-ttu-id="e007e-118">요소</span><span class="sxs-lookup"><span data-stu-id="e007e-118">Element</span></span>|<span data-ttu-id="e007e-119">설명</span><span class="sxs-lookup"><span data-stu-id="e007e-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e007e-120">\<behavior></span><span class="sxs-lookup"><span data-stu-id="e007e-120">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="e007e-121">엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e007e-121">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e007e-122">설명</span><span class="sxs-lookup"><span data-stu-id="e007e-122">Remarks</span></span>  
 <span data-ttu-id="e007e-123">채널 수신기에 기본값(비동기) 대신 동기 수신을 사용하도록 지시하려면 이 동작을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e007e-123">Use this behavior to instruct the channel listener to use a synchronous receive rather than the default, asynchronous.</span></span> <span data-ttu-id="e007e-124">Windows Communication Foundation (WCF)를 수락 된 각 채널에 대해 공급할 새 스레드를 발급 합니다.</span><span class="sxs-lookup"><span data-stu-id="e007e-124">Windows Communication Foundation (WCF) issues a new thread to pump for each accepted channel.</span></span> <span data-ttu-id="e007e-125">채널이 많은 경우 스레드가 부족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e007e-125">If there are a lot of channels, there is the possibility of running out of threads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e007e-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="e007e-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>
- <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
