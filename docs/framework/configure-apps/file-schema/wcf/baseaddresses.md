---
title: <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 7d0afd638e9a311b69ff47b6789d5fde093945ba
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673526"
---
# <a name="baseaddresses"></a><span data-ttu-id="76e2e-101">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="76e2e-101">\<baseAddresses></span></span>
<span data-ttu-id="76e2e-102">자체 호스팅 환경의 서비스 호스트에 대한 기준 주소인 `baseAddress` 요소의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="76e2e-102">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="76e2e-103">기준 주소가 있는 경우 기준 주소에 대한 상대 주소로 엔드포인트를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76e2e-103">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
 <span data-ttu-id="76e2e-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="76e2e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="76e2e-105">\<client></span><span class="sxs-lookup"><span data-stu-id="76e2e-105">\<client></span></span>  
<span data-ttu-id="76e2e-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="76e2e-106">\<endpoint></span></span>  
<span data-ttu-id="76e2e-107">\<host></span><span class="sxs-lookup"><span data-stu-id="76e2e-107">\<host></span></span>  
<span data-ttu-id="76e2e-108">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="76e2e-108">\<baseAddresses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76e2e-109">구문</span><span class="sxs-lookup"><span data-stu-id="76e2e-109">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="76e2e-110">형식</span><span class="sxs-lookup"><span data-stu-id="76e2e-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="76e2e-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="76e2e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="76e2e-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="76e2e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="76e2e-113">특성</span><span class="sxs-lookup"><span data-stu-id="76e2e-113">Attributes</span></span>  
 <span data-ttu-id="76e2e-114">없음</span><span class="sxs-lookup"><span data-stu-id="76e2e-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="76e2e-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="76e2e-115">Child Elements</span></span>  
  
|<span data-ttu-id="76e2e-116">요소</span><span class="sxs-lookup"><span data-stu-id="76e2e-116">Element</span></span>|<span data-ttu-id="76e2e-117">설명</span><span class="sxs-lookup"><span data-stu-id="76e2e-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="76e2e-118">\<add></span><span class="sxs-lookup"><span data-stu-id="76e2e-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md)|<span data-ttu-id="76e2e-119">서비스 호스트에서 사용하는 기본 주소를 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="76e2e-119">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="76e2e-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="76e2e-120">Parent Elements</span></span>  
  
|<span data-ttu-id="76e2e-121">요소</span><span class="sxs-lookup"><span data-stu-id="76e2e-121">Element</span></span>|<span data-ttu-id="76e2e-122">설명</span><span class="sxs-lookup"><span data-stu-id="76e2e-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="76e2e-123">\<host></span><span class="sxs-lookup"><span data-stu-id="76e2e-123">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="76e2e-124">서비스 호스트의 설정을 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="76e2e-124">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="76e2e-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="76e2e-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="76e2e-126">호스팅</span><span class="sxs-lookup"><span data-stu-id="76e2e-126">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
