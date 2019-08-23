---
title: <defaultPorts>
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 462a06e5a773310b6364838ae2ebc14da0a2ee1b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925884"
---
# <a name="defaultports"></a><span data-ttu-id="f55d8-101">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="f55d8-101">\<defaultPorts></span></span>
<span data-ttu-id="f55d8-102">클라이언트 애플리케이션에서 수신하는 기본 통신 엔드포인트를 나열하는 기본 포트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="f55d8-102">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
<span data-ttu-id="f55d8-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f55d8-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="f55d8-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="f55d8-104">\<behaviors></span></span>  
<span data-ttu-id="f55d8-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="f55d8-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="f55d8-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="f55d8-106">\<behavior></span></span>  
<span data-ttu-id="f55d8-107">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="f55d8-107">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="f55d8-108">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="f55d8-108">\<defaultPorts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f55d8-109">구문</span><span class="sxs-lookup"><span data-stu-id="f55d8-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f55d8-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f55d8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f55d8-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f55d8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f55d8-112">특성</span><span class="sxs-lookup"><span data-stu-id="f55d8-112">Attributes</span></span>  
 <span data-ttu-id="f55d8-113">없음</span><span class="sxs-lookup"><span data-stu-id="f55d8-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f55d8-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f55d8-114">Child Elements</span></span>  
  
|<span data-ttu-id="f55d8-115">요소</span><span class="sxs-lookup"><span data-stu-id="f55d8-115">Element</span></span>|<span data-ttu-id="f55d8-116">Description</span><span class="sxs-lookup"><span data-stu-id="f55d8-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f55d8-117">\<defaultports의 \<> 추가 ></span><span class="sxs-lookup"><span data-stu-id="f55d8-117">\<add> of \<defaultPorts></span></span>](add-of-defaultports.md)|<span data-ttu-id="f55d8-118">클라이언트 애플리케이션에서 수신하는 기본 통신 엔드포인트입니다.</span><span class="sxs-lookup"><span data-stu-id="f55d8-118">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f55d8-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f55d8-119">Parent Elements</span></span>  
  
|<span data-ttu-id="f55d8-120">요소</span><span class="sxs-lookup"><span data-stu-id="f55d8-120">Element</span></span>|<span data-ttu-id="f55d8-121">Description</span><span class="sxs-lookup"><span data-stu-id="f55d8-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f55d8-122">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="f55d8-122">\<useRequestHeadersForMetadataAddress></span></span>](userequestheadersformetadataaddress.md)|<span data-ttu-id="f55d8-123">기본 포트의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="f55d8-123">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f55d8-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="f55d8-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
