---
title: <discoveryClient>
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: f9d7e3a4957d2a8f30724f0bfc04e58a57fc5f7d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919266"
---
# <a name="discoveryclient"></a><span data-ttu-id="6b7dd-101">\<discoveryClient></span><span class="sxs-lookup"><span data-stu-id="6b7dd-101">\<discoveryClient></span></span>
<span data-ttu-id="6b7dd-102">클라이언트 애플리케이션에서 런타임에 검색 가능 서비스를 자동으로 검색하고 해당 주소를 찾을 수 있도록 하는 사용자 지정 바인딩을 만들기 위한 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6b7dd-102">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
<span data-ttu-id="6b7dd-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="6b7dd-103">\<system.serviceModel></span></span>  
<span data-ttu-id="6b7dd-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="6b7dd-104">\<bindings></span></span>  
<span data-ttu-id="6b7dd-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="6b7dd-105">\<customBinding></span></span>  
<span data-ttu-id="6b7dd-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="6b7dd-106">\<binding></span></span>  
<span data-ttu-id="6b7dd-107">\<discoveryClient></span><span class="sxs-lookup"><span data-stu-id="6b7dd-107">\<discoveryClient></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b7dd-108">구문</span><span class="sxs-lookup"><span data-stu-id="6b7dd-108">Syntax</span></span>  
  
```xml  
<discoveryClient discoveryEndpoint="String">
  <findCriteria duration="TimeSpan"
                maxResults="Integer"
                scopeMatchBy="Uri">
    <contractTypeNames>
      <add name="String"
           namespace="String" />
    </contractTypeNames>
    <extensions />
    <scopes>
      <add scope="URI"/>
    </scopes>
  </findCriteria>
</discoveryClient>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6b7dd-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="6b7dd-109">Attributes and Elements</span></span>  
 <span data-ttu-id="6b7dd-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6b7dd-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6b7dd-111">특성</span><span class="sxs-lookup"><span data-stu-id="6b7dd-111">Attributes</span></span>  
  
|<span data-ttu-id="6b7dd-112">특성</span><span class="sxs-lookup"><span data-stu-id="6b7dd-112">Attribute</span></span>|<span data-ttu-id="6b7dd-113">Description</span><span class="sxs-lookup"><span data-stu-id="6b7dd-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6b7dd-114">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="6b7dd-114">discoveryEndpoint</span></span>|<span data-ttu-id="6b7dd-115">클라이언트 애플리케이션에서 런타임에 검색 가능한 서비스를 자동으로 검색하고 해당 주소를 찾을 수 있도록 하는 검색 엔드포인트의 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="6b7dd-115">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6b7dd-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6b7dd-116">Child Elements</span></span>  
  
|<span data-ttu-id="6b7dd-117">요소</span><span class="sxs-lookup"><span data-stu-id="6b7dd-117">Element</span></span>|<span data-ttu-id="6b7dd-118">설명</span><span class="sxs-lookup"><span data-stu-id="6b7dd-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6b7dd-119">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="6b7dd-119">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="6b7dd-120">클라이언트 애플리케이션에서 검색 서비스를 찾기 위해 사용하는 조건 집합을 제공하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6b7dd-120">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="6b7dd-121">기준은 검색 조건 (찾으려는 서비스 지정)으로 그룹화 하 고 종료 조건 (검색이 마지막으로 수행 되는 시간)을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b7dd-121">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6b7dd-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6b7dd-122">Parent Elements</span></span>  
  
|<span data-ttu-id="6b7dd-123">요소</span><span class="sxs-lookup"><span data-stu-id="6b7dd-123">Element</span></span>|<span data-ttu-id="6b7dd-124">설명</span><span class="sxs-lookup"><span data-stu-id="6b7dd-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6b7dd-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="6b7dd-125">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="6b7dd-126">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6b7dd-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6b7dd-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="6b7dd-127">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
