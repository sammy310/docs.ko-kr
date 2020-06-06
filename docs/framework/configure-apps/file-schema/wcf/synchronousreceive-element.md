---
title: <synchronousReceive> 요소
ms.date: 03/30/2017
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
ms.openlocfilehash: b3f4860be6b7edac776a1c30611271b2eb36968e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399505"
---
# <a name="synchronousreceive-element"></a><span data-ttu-id="5a0b0-102">\<synchronousReceive> 요소</span><span class="sxs-lookup"><span data-stu-id="5a0b0-102">\<synchronousReceive> element</span></span>
<span data-ttu-id="5a0b0-103">이 구성 요소는 서비스 또는 클라이언트 애플리케이션에서 메시지 수신을 위한 런타임 동작을 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a0b0-103">This configuration element is used to specify run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="5a0b0-104">이 구성 요소에는 특성이나 자식 요소가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5a0b0-104">It does not have any attributes or child elements.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<synchronousReceive>**  
  
## <a name="syntax"></a><span data-ttu-id="5a0b0-105">구문</span><span class="sxs-lookup"><span data-stu-id="5a0b0-105">Syntax</span></span>  
  
```xml  
<synchronousReceive />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5a0b0-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5a0b0-106">Attributes and Elements</span></span>  
 <span data-ttu-id="5a0b0-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5a0b0-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5a0b0-108">특성</span><span class="sxs-lookup"><span data-stu-id="5a0b0-108">Attributes</span></span>  
 <span data-ttu-id="5a0b0-109">없음</span><span class="sxs-lookup"><span data-stu-id="5a0b0-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5a0b0-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5a0b0-110">Child Elements</span></span>  
 <span data-ttu-id="5a0b0-111">없음</span><span class="sxs-lookup"><span data-stu-id="5a0b0-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5a0b0-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5a0b0-112">Parent Elements</span></span>  
  
|<span data-ttu-id="5a0b0-113">요소</span><span class="sxs-lookup"><span data-stu-id="5a0b0-113">Element</span></span>|<span data-ttu-id="5a0b0-114">Description</span><span class="sxs-lookup"><span data-stu-id="5a0b0-114">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="5a0b0-115">엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5a0b0-115">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a0b0-116">설명</span><span class="sxs-lookup"><span data-stu-id="5a0b0-116">Remarks</span></span>  
 <span data-ttu-id="5a0b0-117">채널 수신기에 기본값(비동기) 대신 동기 수신을 사용하도록 지시하려면 이 동작을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5a0b0-117">Use this behavior to instruct the channel listener to use a synchronous receive rather than the default, asynchronous.</span></span> <span data-ttu-id="5a0b0-118">WCF (Windows Communication Foundation)는 수락 된 각 채널에 대해 펌프 하기 위해 새 스레드를 발급 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a0b0-118">Windows Communication Foundation (WCF) issues a new thread to pump for each accepted channel.</span></span> <span data-ttu-id="5a0b0-119">채널이 많은 경우 스레드가 부족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a0b0-119">If there are a lot of channels, there is the possibility of running out of threads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a0b0-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5a0b0-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>
- <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
