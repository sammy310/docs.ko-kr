---
title: <synchronousReceive> 요소
ms.date: 03/30/2017
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
ms.openlocfilehash: fa14d4606303b2d67cf5ef845d428bb086680204
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938960"
---
# <a name="synchronousreceive-element"></a><span data-ttu-id="a3f46-102">\<synchronousReceive > 요소</span><span class="sxs-lookup"><span data-stu-id="a3f46-102">\<synchronousReceive> element</span></span>
<span data-ttu-id="a3f46-103">이 구성 요소는 서비스 또는 클라이언트 애플리케이션에서 메시지 수신을 위한 런타임 동작을 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3f46-103">This configuration element is used to specify run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="a3f46-104">이 구성 요소에는 특성이나 자식 요소가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a3f46-104">It does not have any attributes or child elements.</span></span>  
  
 <span data-ttu-id="a3f46-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a3f46-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="a3f46-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="a3f46-106">\<behaviors></span></span>  
<span data-ttu-id="a3f46-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="a3f46-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="a3f46-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="a3f46-108">\<behavior></span></span>  
<span data-ttu-id="a3f46-109">\<synchronousReceive></span><span class="sxs-lookup"><span data-stu-id="a3f46-109">\<synchronousReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3f46-110">구문</span><span class="sxs-lookup"><span data-stu-id="a3f46-110">Syntax</span></span>  
  
```xml  
<synchronousReceive />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a3f46-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a3f46-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a3f46-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a3f46-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a3f46-113">특성</span><span class="sxs-lookup"><span data-stu-id="a3f46-113">Attributes</span></span>  
 <span data-ttu-id="a3f46-114">없음</span><span class="sxs-lookup"><span data-stu-id="a3f46-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a3f46-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a3f46-115">Child Elements</span></span>  
 <span data-ttu-id="a3f46-116">없음</span><span class="sxs-lookup"><span data-stu-id="a3f46-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a3f46-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a3f46-117">Parent Elements</span></span>  
  
|<span data-ttu-id="a3f46-118">요소</span><span class="sxs-lookup"><span data-stu-id="a3f46-118">Element</span></span>|<span data-ttu-id="a3f46-119">설명</span><span class="sxs-lookup"><span data-stu-id="a3f46-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a3f46-120">\<behavior></span><span class="sxs-lookup"><span data-stu-id="a3f46-120">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="a3f46-121">엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a3f46-121">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3f46-122">설명</span><span class="sxs-lookup"><span data-stu-id="a3f46-122">Remarks</span></span>  
 <span data-ttu-id="a3f46-123">채널 수신기에 기본값(비동기) 대신 동기 수신을 사용하도록 지시하려면 이 동작을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a3f46-123">Use this behavior to instruct the channel listener to use a synchronous receive rather than the default, asynchronous.</span></span> <span data-ttu-id="a3f46-124">WCF (Windows Communication Foundation)는 수락 된 각 채널에 대해 펌프 하기 위해 새 스레드를 발급 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3f46-124">Windows Communication Foundation (WCF) issues a new thread to pump for each accepted channel.</span></span> <span data-ttu-id="a3f46-125">채널이 많은 경우 스레드가 부족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3f46-125">If there are a lot of channels, there is the possibility of running out of threads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3f46-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="a3f46-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>
- <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
