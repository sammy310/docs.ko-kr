---
title: <findCriteria>
ms.date: 03/30/2017
ms.assetid: 5454cd19-6bf5-4ba8-94d1-f58d10dc1917
ms.openlocfilehash: eb8ff3905f7696f4c71a79e31db1b8f82c9f0d3b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925591"
---
# <a name="findcriteria"></a><span data-ttu-id="b0a29-101">\<findCriteria></span><span class="sxs-lookup"><span data-stu-id="b0a29-101">\<findCriteria></span></span>
<span data-ttu-id="b0a29-102">클라이언트 애플리케이션에서 검색 서비스를 찾기 위해 사용하는 조건 집합을 제공하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b0a29-102">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="b0a29-103">기준은 검색 조건 (찾으려는 서비스 지정)으로 그룹화 하 고 종료 조건 (검색이 마지막으로 수행 되는 시간)을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0a29-103">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>  
  
 <span data-ttu-id="b0a29-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b0a29-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b0a29-105">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="b0a29-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0a29-106">구문</span><span class="sxs-lookup"><span data-stu-id="b0a29-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <dynamicEndpoint>
      <standardEndpoint>
        <discoveryClientSettings discoveryEndpoint="String">
          <findCriteria duration="TimeSpan"
                        maxResults="Integer"
                        scopeMatchBy="Uri">
            <contractTypeNames>
              <add name="String"
                   namespace="String" />
            </contractTypeNames>
            <extensions />
            <scopes>
              <add scope="URI" />
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      </standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b0a29-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b0a29-107">Attributes and Elements</span></span>  
 <span data-ttu-id="b0a29-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a29-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b0a29-109">특성</span><span class="sxs-lookup"><span data-stu-id="b0a29-109">Attributes</span></span>  
  
|<span data-ttu-id="b0a29-110">특성</span><span class="sxs-lookup"><span data-stu-id="b0a29-110">Attribute</span></span>|<span data-ttu-id="b0a29-111">설명</span><span class="sxs-lookup"><span data-stu-id="b0a29-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b0a29-112">duration</span><span class="sxs-lookup"><span data-stu-id="b0a29-112">duration</span></span>|<span data-ttu-id="b0a29-113">네트워크에서 서비스로부터 응답을 기다리는 최대 시간을 지정하는 Timespan 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b0a29-113">A Timespan value that specifies the maximum time to wait for replies from services on the network.</span></span> <span data-ttu-id="b0a29-114">기본 시간은 20초입니다.</span><span class="sxs-lookup"><span data-stu-id="b0a29-114">The default duration is 20 seconds.</span></span>|  
|<span data-ttu-id="b0a29-115">maxResults</span><span class="sxs-lookup"><span data-stu-id="b0a29-115">maxResults</span></span>|<span data-ttu-id="b0a29-116">네트워크 또는 인터넷에서 서비스로부터 기다리는 최대 응답 횟수를 지정하는 정수입니다</span><span class="sxs-lookup"><span data-stu-id="b0a29-116">An integer that specifies the maximum number of replies to wait for, from services on a network or the Internet.</span></span> <span data-ttu-id="b0a29-117">`duration` 특성에 지정된 시간이 경과되기 전에 최대 응답이 수신되는 경우 찾기 작업이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0a29-117">If maximum replies are received before the value specified in the `duration` attribute has elapsed, the find operation ends.</span></span>|  
|<span data-ttu-id="b0a29-118">scopeMatchBy</span><span class="sxs-lookup"><span data-stu-id="b0a29-118">scopeMatchBy</span></span>|<span data-ttu-id="b0a29-119">Probe 메시지의 범위와 엔드포인트의 범위를 일치시키는 동안 사용할 일치 알고리즘을 지정하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="b0a29-119">A URI that specify the matching algorithm to use while matching the scopes in the Probe message with that of the endpoint.</span></span><br /><br /> <span data-ttu-id="b0a29-120">다섯 가지의 범위 일치 규칙이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0a29-120">There are five supported scope-matching rules.</span></span> <span data-ttu-id="b0a29-121">범위 일치 규칙을 지정하지 않으면 `ScopeMatchByPrefix`가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0a29-121">If you do not specify a scope-matching rule, `ScopeMatchByPrefix` is used.</span></span> <span data-ttu-id="b0a29-122">이에 대한 자세한 내용은 <xref:System.ServiceModel.Discovery.FindCriteria>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0a29-122">For more information on this, see <xref:System.ServiceModel.Discovery.FindCriteria>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b0a29-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b0a29-123">Child Elements</span></span>  
  
|<span data-ttu-id="b0a29-124">요소</span><span class="sxs-lookup"><span data-stu-id="b0a29-124">Element</span></span>|<span data-ttu-id="b0a29-125">Description</span><span class="sxs-lookup"><span data-stu-id="b0a29-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b0a29-126">\<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="b0a29-126">\<contractTypeNames></span></span>](contracttypenames.md)|<span data-ttu-id="b0a29-127">워크플로 서비스 계약 형식의 이름을 포함 하는 구성 요소 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="b0a29-127">A collection of configuration elements that contain the names of workflow service contract types.</span></span>|  
|<span data-ttu-id="b0a29-128">\<findcriteria의 \<확장 > ></span><span class="sxs-lookup"><span data-stu-id="b0a29-128">\<extensions> of \<findCriteria></span></span>|<span data-ttu-id="b0a29-129">확장을 제공하는 XML 요소 개체의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="b0a29-129">A collection of XML element objects that provide extensions.</span></span>|  
|[<span data-ttu-id="b0a29-130">\<scopes></span><span class="sxs-lookup"><span data-stu-id="b0a29-130">\<scopes></span></span>](scopes.md)|<span data-ttu-id="b0a29-131">찾기 작업 중에 특정 서비스를 찾기 위해 사용하는 절대 URI를 포함하는 개체의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="b0a29-131">A collection of objects that contain absolute URIs that are used during a find operation to locate a specific service or services.</span></span><br /><br /> <span data-ttu-id="b0a29-132">특정 서비스를 찾으면 서비스 URI와 범위 URI 간에 성공한 일치 항목이 생깁니다. 이때 경우에 따라 일치의 복잡한 문제를 처리하는 범위 규칙이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0a29-132">If the specific service is found, a successful match has been made between the service URI and the Scope URI, sometimes with the help of scope rules that handle complications of matching.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b0a29-133">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b0a29-133">Parent Elements</span></span>  
  
|<span data-ttu-id="b0a29-134">요소</span><span class="sxs-lookup"><span data-stu-id="b0a29-134">Element</span></span>|<span data-ttu-id="b0a29-135">설명</span><span class="sxs-lookup"><span data-stu-id="b0a29-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b0a29-136">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="b0a29-136">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="b0a29-137">애플리케이션에서 서비스 검색 프로세스에 클라이언트로 참여하기 위해 필요한 설정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0a29-137">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b0a29-138">참고자료</span><span class="sxs-lookup"><span data-stu-id="b0a29-138">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
