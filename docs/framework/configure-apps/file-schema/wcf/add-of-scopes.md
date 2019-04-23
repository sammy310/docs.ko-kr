---
title: <scopes>의 <add>
ms.date: 03/30/2017
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
ms.openlocfilehash: c29e47f688118e34fbdb4deb396c930d478f0582
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59187086"
---
# <a name="add-of-scopes"></a><span data-ttu-id="145da-102">\<추가 >의 \<범위 ></span><span class="sxs-lookup"><span data-stu-id="145da-102">\<add> of \<scopes></span></span>
<span data-ttu-id="145da-103">쿼리 중에 서비스 엔드포인트를 필터링하기 위해 사용할 수 있는 사용자 지정 범위 URI를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="145da-103">Adds a custom scope Uri that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="145da-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="145da-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="145da-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="145da-105">\<behaviors></span></span>  
<span data-ttu-id="145da-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="145da-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="145da-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="145da-107">\<behavior></span></span>  
<span data-ttu-id="145da-108">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="145da-108">\<endpointDiscovery></span></span>  
<span data-ttu-id="145da-109">\<scopes></span><span class="sxs-lookup"><span data-stu-id="145da-109">\<scopes></span></span>  
<span data-ttu-id="145da-110">\<add></span><span class="sxs-lookup"><span data-stu-id="145da-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="145da-111">구문</span><span class="sxs-lookup"><span data-stu-id="145da-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="145da-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="145da-112">Attributes and Elements</span></span>  
 <span data-ttu-id="145da-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="145da-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="145da-114">특성</span><span class="sxs-lookup"><span data-stu-id="145da-114">Attributes</span></span>  
  
|<span data-ttu-id="145da-115">특성</span><span class="sxs-lookup"><span data-stu-id="145da-115">Attribute</span></span>|<span data-ttu-id="145da-116">설명</span><span class="sxs-lookup"><span data-stu-id="145da-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="145da-117">범위</span><span class="sxs-lookup"><span data-stu-id="145da-117">scope</span></span>|<span data-ttu-id="145da-118">서비스를 찾기 위한 일치 기준으로 사용할 수 있는 엔드포인트의 범위 정보가 포함되는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="145da-118">A URI that contains scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="145da-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="145da-119">Child Elements</span></span>  
 <span data-ttu-id="145da-120">없음</span><span class="sxs-lookup"><span data-stu-id="145da-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="145da-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="145da-121">Parent Elements</span></span>  
  
|<span data-ttu-id="145da-122">요소</span><span class="sxs-lookup"><span data-stu-id="145da-122">Element</span></span>|<span data-ttu-id="145da-123">설명</span><span class="sxs-lookup"><span data-stu-id="145da-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="145da-124">\<scopes></span><span class="sxs-lookup"><span data-stu-id="145da-124">\<scopes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|<span data-ttu-id="145da-125">쿼리 중에 서비스 엔드포인트를 필터링하기 위해 사용할 수 있는 사용자 지정 범위 URI를 지정하는 구성 요소의 컬렉션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="145da-125">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="145da-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="145da-126">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
