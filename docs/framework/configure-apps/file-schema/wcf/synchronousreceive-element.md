---
title: <synchronousReceive> 요소
ms.date: 03/30/2017
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
ms.openlocfilehash: b3f4860be6b7edac776a1c30611271b2eb36968e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399505"
---
# <a name="synchronousreceive-element"></a><span data-ttu-id="973aa-102">\<synchronousReceive > 요소</span><span class="sxs-lookup"><span data-stu-id="973aa-102">\<synchronousReceive> element</span></span>
<span data-ttu-id="973aa-103">이 구성 요소는 서비스 또는 클라이언트 애플리케이션에서 메시지 수신을 위한 런타임 동작을 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="973aa-103">This configuration element is used to specify run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="973aa-104">이 구성 요소에는 특성이나 자식 요소가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="973aa-104">It does not have any attributes or child elements.</span></span>  
  
<span data-ttu-id="973aa-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="973aa-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="973aa-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="973aa-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="973aa-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="973aa-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="973aa-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="973aa-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="973aa-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="973aa-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="973aa-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<synchronousReceive >**</span><span class="sxs-lookup"><span data-stu-id="973aa-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<synchronousReceive>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="973aa-111">구문</span><span class="sxs-lookup"><span data-stu-id="973aa-111">Syntax</span></span>  
  
```xml  
<synchronousReceive />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="973aa-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="973aa-112">Attributes and Elements</span></span>  
 <span data-ttu-id="973aa-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="973aa-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="973aa-114">특성</span><span class="sxs-lookup"><span data-stu-id="973aa-114">Attributes</span></span>  
 <span data-ttu-id="973aa-115">없음</span><span class="sxs-lookup"><span data-stu-id="973aa-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="973aa-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="973aa-116">Child Elements</span></span>  
 <span data-ttu-id="973aa-117">없음</span><span class="sxs-lookup"><span data-stu-id="973aa-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="973aa-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="973aa-118">Parent Elements</span></span>  
  
|<span data-ttu-id="973aa-119">요소</span><span class="sxs-lookup"><span data-stu-id="973aa-119">Element</span></span>|<span data-ttu-id="973aa-120">설명</span><span class="sxs-lookup"><span data-stu-id="973aa-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="973aa-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="973aa-121">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="973aa-122">엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="973aa-122">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="973aa-123">설명</span><span class="sxs-lookup"><span data-stu-id="973aa-123">Remarks</span></span>  
 <span data-ttu-id="973aa-124">채널 수신기에 기본값(비동기) 대신 동기 수신을 사용하도록 지시하려면 이 동작을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="973aa-124">Use this behavior to instruct the channel listener to use a synchronous receive rather than the default, asynchronous.</span></span> <span data-ttu-id="973aa-125">WCF (Windows Communication Foundation)는 수락 된 각 채널에 대해 펌프 하기 위해 새 스레드를 발급 합니다.</span><span class="sxs-lookup"><span data-stu-id="973aa-125">Windows Communication Foundation (WCF) issues a new thread to pump for each accepted channel.</span></span> <span data-ttu-id="973aa-126">채널이 많은 경우 스레드가 부족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="973aa-126">If there are a lot of channels, there is the possibility of running out of threads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="973aa-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="973aa-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>
- <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
