---
description: '다음에 대 한 자세한 정보: <synchronousReceive> 요소'
title: <synchronousReceive> 요소
ms.date: 03/30/2017
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
ms.openlocfilehash: afcd10b4ad41bd6ff12dbf246f66ef7fac4e759a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99682620"
---
# <a name="synchronousreceive-element"></a><span data-ttu-id="5ed8d-103">\<synchronousReceive> 요소</span><span class="sxs-lookup"><span data-stu-id="5ed8d-103">\<synchronousReceive> element</span></span>

<span data-ttu-id="5ed8d-104">이 구성 요소는 서비스 또는 클라이언트 애플리케이션에서 메시지 수신을 위한 런타임 동작을 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ed8d-104">This configuration element is used to specify run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="5ed8d-105">이 구성 요소에는 특성이나 자식 요소가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5ed8d-105">It does not have any attributes or child elements.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<synchronousReceive>**  
  
## <a name="syntax"></a><span data-ttu-id="5ed8d-106">구문</span><span class="sxs-lookup"><span data-stu-id="5ed8d-106">Syntax</span></span>  
  
```xml  
<synchronousReceive />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5ed8d-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5ed8d-107">Attributes and Elements</span></span>  

 <span data-ttu-id="5ed8d-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5ed8d-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5ed8d-109">특성</span><span class="sxs-lookup"><span data-stu-id="5ed8d-109">Attributes</span></span>  

 <span data-ttu-id="5ed8d-110">없음</span><span class="sxs-lookup"><span data-stu-id="5ed8d-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5ed8d-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5ed8d-111">Child Elements</span></span>  

 <span data-ttu-id="5ed8d-112">없음</span><span class="sxs-lookup"><span data-stu-id="5ed8d-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5ed8d-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5ed8d-113">Parent Elements</span></span>  
  
|<span data-ttu-id="5ed8d-114">요소</span><span class="sxs-lookup"><span data-stu-id="5ed8d-114">Element</span></span>|<span data-ttu-id="5ed8d-115">설명</span><span class="sxs-lookup"><span data-stu-id="5ed8d-115">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="5ed8d-116">엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5ed8d-116">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ed8d-117">설명</span><span class="sxs-lookup"><span data-stu-id="5ed8d-117">Remarks</span></span>  

 <span data-ttu-id="5ed8d-118">채널 수신기에 기본값(비동기) 대신 동기 수신을 사용하도록 지시하려면 이 동작을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5ed8d-118">Use this behavior to instruct the channel listener to use a synchronous receive rather than the default, asynchronous.</span></span> <span data-ttu-id="5ed8d-119">WCF (Windows Communication Foundation)는 수락 된 각 채널에 대해 펌프 하기 위해 새 스레드를 발급 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ed8d-119">Windows Communication Foundation (WCF) issues a new thread to pump for each accepted channel.</span></span> <span data-ttu-id="5ed8d-120">채널이 많은 경우 스레드가 부족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ed8d-120">If there are a lot of channels, there is the possibility of running out of threads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ed8d-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5ed8d-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>
- <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
