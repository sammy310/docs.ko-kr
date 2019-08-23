---
title: <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 059ea4e637ab906d1fde9807a73ac8341f81c574
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926420"
---
# <a name="baseaddresses"></a><span data-ttu-id="15efa-101">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="15efa-101">\<baseAddresses></span></span>
<span data-ttu-id="15efa-102">자체 호스팅 환경의 서비스 호스트에 대한 기준 주소인 `baseAddress` 요소의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="15efa-102">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="15efa-103">기준 주소가 있는 경우 기준 주소에 대한 상대 주소로 엔드포인트를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15efa-103">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
 <span data-ttu-id="15efa-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="15efa-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="15efa-105">\<client></span><span class="sxs-lookup"><span data-stu-id="15efa-105">\<client></span></span>  
<span data-ttu-id="15efa-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="15efa-106">\<endpoint></span></span>  
<span data-ttu-id="15efa-107">\<host></span><span class="sxs-lookup"><span data-stu-id="15efa-107">\<host></span></span>  
<span data-ttu-id="15efa-108">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="15efa-108">\<baseAddresses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15efa-109">구문</span><span class="sxs-lookup"><span data-stu-id="15efa-109">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="15efa-110">형식</span><span class="sxs-lookup"><span data-stu-id="15efa-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="15efa-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="15efa-111">Attributes and Elements</span></span>  
 <span data-ttu-id="15efa-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="15efa-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="15efa-113">특성</span><span class="sxs-lookup"><span data-stu-id="15efa-113">Attributes</span></span>  
 <span data-ttu-id="15efa-114">없음</span><span class="sxs-lookup"><span data-stu-id="15efa-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="15efa-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="15efa-115">Child Elements</span></span>  
  
|<span data-ttu-id="15efa-116">요소</span><span class="sxs-lookup"><span data-stu-id="15efa-116">Element</span></span>|<span data-ttu-id="15efa-117">설명</span><span class="sxs-lookup"><span data-stu-id="15efa-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="15efa-118">\<add></span><span class="sxs-lookup"><span data-stu-id="15efa-118">\<add></span></span>](add-of-baseaddresses.md)|<span data-ttu-id="15efa-119">서비스 호스트에서 사용하는 기본 주소를 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="15efa-119">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="15efa-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="15efa-120">Parent Elements</span></span>  
  
|<span data-ttu-id="15efa-121">요소</span><span class="sxs-lookup"><span data-stu-id="15efa-121">Element</span></span>|<span data-ttu-id="15efa-122">설명</span><span class="sxs-lookup"><span data-stu-id="15efa-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="15efa-123">\<host></span><span class="sxs-lookup"><span data-stu-id="15efa-123">\<host></span></span>](host.md)|<span data-ttu-id="15efa-124">서비스 호스트의 설정을 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="15efa-124">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="15efa-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="15efa-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="15efa-126">호스팅</span><span class="sxs-lookup"><span data-stu-id="15efa-126">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
