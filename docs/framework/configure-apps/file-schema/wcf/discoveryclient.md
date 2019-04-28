---
title: <discoveryClient>
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: a5ea10601732021af578c17d4f5c5ab69c98f17a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704026"
---
# <a name="discoveryclient"></a><span data-ttu-id="fa36a-101">\<discoveryClient></span><span class="sxs-lookup"><span data-stu-id="fa36a-101">\<discoveryClient></span></span>
<span data-ttu-id="fa36a-102">클라이언트 응용 프로그램에서 런타임에 검색 가능 서비스를 자동으로 검색하고 해당 주소를 찾을 수 있도록 하는 사용자 지정 바인딩을 만들기 위한 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="fa36a-102">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
<span data-ttu-id="fa36a-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="fa36a-103">\<system.serviceModel></span></span>  
<span data-ttu-id="fa36a-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="fa36a-104">\<bindings></span></span>  
<span data-ttu-id="fa36a-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="fa36a-105">\<customBinding></span></span>  
<span data-ttu-id="fa36a-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="fa36a-106">\<binding></span></span>  
<span data-ttu-id="fa36a-107">\<discoveryClient></span><span class="sxs-lookup"><span data-stu-id="fa36a-107">\<discoveryClient></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa36a-108">구문</span><span class="sxs-lookup"><span data-stu-id="fa36a-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fa36a-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="fa36a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="fa36a-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fa36a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fa36a-111">특성</span><span class="sxs-lookup"><span data-stu-id="fa36a-111">Attributes</span></span>  
  
|<span data-ttu-id="fa36a-112">특성</span><span class="sxs-lookup"><span data-stu-id="fa36a-112">Attribute</span></span>|<span data-ttu-id="fa36a-113">설명</span><span class="sxs-lookup"><span data-stu-id="fa36a-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fa36a-114">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="fa36a-114">discoveryEndpoint</span></span>|<span data-ttu-id="fa36a-115">클라이언트 응용 프로그램에서 런타임에 검색 가능한 서비스를 자동으로 검색하고 해당 주소를 찾을 수 있도록 하는 검색 엔드포인트의 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="fa36a-115">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fa36a-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="fa36a-116">Child Elements</span></span>  
  
|<span data-ttu-id="fa36a-117">요소</span><span class="sxs-lookup"><span data-stu-id="fa36a-117">Element</span></span>|<span data-ttu-id="fa36a-118">설명</span><span class="sxs-lookup"><span data-stu-id="fa36a-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa36a-119">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="fa36a-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="fa36a-120">클라이언트 응용 프로그램에서 검색 서비스를 찾기 위해 사용하는 조건 집합을 제공하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="fa36a-120">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="fa36a-121">조건 (찾으려는 서비스 지정) 하는 검색 조건으로 그룹화 할 수 있습니다 및 찾기 종료 조건 (검색 지속 기간).</span><span class="sxs-lookup"><span data-stu-id="fa36a-121">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fa36a-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="fa36a-122">Parent Elements</span></span>  
  
|<span data-ttu-id="fa36a-123">요소</span><span class="sxs-lookup"><span data-stu-id="fa36a-123">Element</span></span>|<span data-ttu-id="fa36a-124">설명</span><span class="sxs-lookup"><span data-stu-id="fa36a-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa36a-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="fa36a-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="fa36a-126">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fa36a-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fa36a-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="fa36a-127">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
