---
title: <scopes>
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: 8bc720238ca3039106345783381cd26134fc46b5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670627"
---
# <a name="scopes"></a><span data-ttu-id="0c107-101">\<scopes></span><span class="sxs-lookup"><span data-stu-id="0c107-101">\<scopes></span></span>
<span data-ttu-id="0c107-102">쿼리 중에 서비스 엔드포인트를 필터링하기 위해 사용할 수 있는 사용자 지정 범위 URI를 지정하는 구성 요소의 컬렉션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0c107-102">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="0c107-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0c107-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="0c107-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="0c107-104">\<behaviors></span></span>  
<span data-ttu-id="0c107-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="0c107-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="0c107-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="0c107-106">\<behavior></span></span>  
<span data-ttu-id="0c107-107">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="0c107-107">\<endpointDiscovery></span></span>  
<span data-ttu-id="0c107-108">\<scopes></span><span class="sxs-lookup"><span data-stu-id="0c107-108">\<scopes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c107-109">구문</span><span class="sxs-lookup"><span data-stu-id="0c107-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0c107-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0c107-110">Attributes and Elements</span></span>  
 <span data-ttu-id="0c107-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0c107-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0c107-112">특성</span><span class="sxs-lookup"><span data-stu-id="0c107-112">Attributes</span></span>  
 <span data-ttu-id="0c107-113">없음</span><span class="sxs-lookup"><span data-stu-id="0c107-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0c107-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0c107-114">Child Elements</span></span>  
  
|<span data-ttu-id="0c107-115">특성</span><span class="sxs-lookup"><span data-stu-id="0c107-115">Attribute</span></span>|<span data-ttu-id="0c107-116">설명</span><span class="sxs-lookup"><span data-stu-id="0c107-116">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="0c107-117">\<add></span><span class="sxs-lookup"><span data-stu-id="0c107-117">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopes.md)|<span data-ttu-id="0c107-118">서비스를 찾기 위한 일치 기준으로 사용할 수 있는 엔드포인트의 범위 정보를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0c107-118">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0c107-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0c107-119">Parent Elements</span></span>  
  
|<span data-ttu-id="0c107-120">요소</span><span class="sxs-lookup"><span data-stu-id="0c107-120">Element</span></span>|<span data-ttu-id="0c107-121">설명</span><span class="sxs-lookup"><span data-stu-id="0c107-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0c107-122">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="0c107-122">\<endpointDiscovery></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|<span data-ttu-id="0c107-123">검색 기능, 범위 및 해당 메타데이터에 대한 사용자 지정 확장 등 엔드포인트에 대한 다양한 검색 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0c107-123">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0c107-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="0c107-124">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
