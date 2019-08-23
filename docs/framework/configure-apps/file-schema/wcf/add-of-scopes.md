---
title: <scopes>의 <add>
ms.date: 03/30/2017
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
ms.openlocfilehash: b190cb72e21d47bdc62aab2daba0f6eea1ee04ac
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926625"
---
# <a name="add-of-scopes"></a><span data-ttu-id="e7220-102">\<\<범위 > 추가 ></span><span class="sxs-lookup"><span data-stu-id="e7220-102">\<add> of \<scopes></span></span>
<span data-ttu-id="e7220-103">쿼리 중에 서비스 엔드포인트를 필터링하기 위해 사용할 수 있는 사용자 지정 범위 URI를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e7220-103">Adds a custom scope Uri that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="e7220-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e7220-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e7220-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="e7220-105">\<behaviors></span></span>  
<span data-ttu-id="e7220-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="e7220-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="e7220-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="e7220-107">\<behavior></span></span>  
<span data-ttu-id="e7220-108">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="e7220-108">\<endpointDiscovery></span></span>  
<span data-ttu-id="e7220-109">\<scopes></span><span class="sxs-lookup"><span data-stu-id="e7220-109">\<scopes></span></span>  
<span data-ttu-id="e7220-110">\<add></span><span class="sxs-lookup"><span data-stu-id="e7220-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7220-111">구문</span><span class="sxs-lookup"><span data-stu-id="e7220-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e7220-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e7220-112">Attributes and Elements</span></span>  
 <span data-ttu-id="e7220-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e7220-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e7220-114">특성</span><span class="sxs-lookup"><span data-stu-id="e7220-114">Attributes</span></span>  
  
|<span data-ttu-id="e7220-115">특성</span><span class="sxs-lookup"><span data-stu-id="e7220-115">Attribute</span></span>|<span data-ttu-id="e7220-116">설명</span><span class="sxs-lookup"><span data-stu-id="e7220-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e7220-117">범위</span><span class="sxs-lookup"><span data-stu-id="e7220-117">scope</span></span>|<span data-ttu-id="e7220-118">서비스를 찾기 위한 일치 기준으로 사용할 수 있는 엔드포인트의 범위 정보가 포함되는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="e7220-118">A URI that contains scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e7220-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e7220-119">Child Elements</span></span>  
 <span data-ttu-id="e7220-120">없음</span><span class="sxs-lookup"><span data-stu-id="e7220-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e7220-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e7220-121">Parent Elements</span></span>  
  
|<span data-ttu-id="e7220-122">요소</span><span class="sxs-lookup"><span data-stu-id="e7220-122">Element</span></span>|<span data-ttu-id="e7220-123">Description</span><span class="sxs-lookup"><span data-stu-id="e7220-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e7220-124">\<scopes></span><span class="sxs-lookup"><span data-stu-id="e7220-124">\<scopes></span></span>](scopes.md)|<span data-ttu-id="e7220-125">쿼리 중에 서비스 엔드포인트를 필터링하기 위해 사용할 수 있는 사용자 지정 범위 URI를 지정하는 구성 요소의 컬렉션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e7220-125">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e7220-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="e7220-126">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
