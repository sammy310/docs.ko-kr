---
title: <scopes>
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: dd6513930798e9e1ab263f75c9350511c2dcdcd5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69935177"
---
# <a name="scopes"></a><span data-ttu-id="2a0f6-101">\<scopes></span><span class="sxs-lookup"><span data-stu-id="2a0f6-101">\<scopes></span></span>
<span data-ttu-id="2a0f6-102">쿼리 중에 서비스 엔드포인트를 필터링하기 위해 사용할 수 있는 사용자 지정 범위 URI를 지정하는 구성 요소의 컬렉션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2a0f6-102">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="2a0f6-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2a0f6-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="2a0f6-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="2a0f6-104">\<behaviors></span></span>  
<span data-ttu-id="2a0f6-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="2a0f6-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="2a0f6-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="2a0f6-106">\<behavior></span></span>  
<span data-ttu-id="2a0f6-107">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="2a0f6-107">\<endpointDiscovery></span></span>  
<span data-ttu-id="2a0f6-108">\<scopes></span><span class="sxs-lookup"><span data-stu-id="2a0f6-108">\<scopes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a0f6-109">구문</span><span class="sxs-lookup"><span data-stu-id="2a0f6-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enable="Boolean">
        <scopes>
          <add scope="URI" />
        </scopes>
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2a0f6-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2a0f6-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2a0f6-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2a0f6-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2a0f6-112">특성</span><span class="sxs-lookup"><span data-stu-id="2a0f6-112">Attributes</span></span>  
 <span data-ttu-id="2a0f6-113">없음</span><span class="sxs-lookup"><span data-stu-id="2a0f6-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2a0f6-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2a0f6-114">Child Elements</span></span>  
  
|<span data-ttu-id="2a0f6-115">특성</span><span class="sxs-lookup"><span data-stu-id="2a0f6-115">Attribute</span></span>|<span data-ttu-id="2a0f6-116">Description</span><span class="sxs-lookup"><span data-stu-id="2a0f6-116">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="2a0f6-117">\<add></span><span class="sxs-lookup"><span data-stu-id="2a0f6-117">\<add></span></span>](add-of-scopes.md)|<span data-ttu-id="2a0f6-118">서비스를 찾기 위한 일치 기준으로 사용할 수 있는 엔드포인트의 범위 정보를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2a0f6-118">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2a0f6-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2a0f6-119">Parent Elements</span></span>  
  
|<span data-ttu-id="2a0f6-120">요소</span><span class="sxs-lookup"><span data-stu-id="2a0f6-120">Element</span></span>|<span data-ttu-id="2a0f6-121">Description</span><span class="sxs-lookup"><span data-stu-id="2a0f6-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2a0f6-122">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="2a0f6-122">\<endpointDiscovery></span></span>](endpointdiscovery.md)|<span data-ttu-id="2a0f6-123">검색 기능, 범위 및 해당 메타데이터에 대한 사용자 지정 확장 등 엔드포인트에 대한 다양한 검색 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2a0f6-123">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2a0f6-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="2a0f6-124">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
