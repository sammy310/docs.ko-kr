---
title: <findCriteria>
ms.date: 03/30/2017
ms.assetid: 5454cd19-6bf5-4ba8-94d1-f58d10dc1917
ms.openlocfilehash: 44e068ee205bc5e04382164e7ab00716b2c07dcf
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855158"
---
# <a name="findcriteria"></a><span data-ttu-id="21ac0-101">\<findCriteria></span><span class="sxs-lookup"><span data-stu-id="21ac0-101">\<findCriteria></span></span>
<span data-ttu-id="21ac0-102">클라이언트 애플리케이션에서 검색 서비스를 찾기 위해 사용하는 조건 집합을 제공하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="21ac0-102">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="21ac0-103">기준은 검색 조건 (찾으려는 서비스 지정)으로 그룹화 하 고 종료 조건 (검색이 마지막으로 수행 되는 시간)을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21ac0-103">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>  
  
<span data-ttu-id="21ac0-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="21ac0-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="21ac0-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="21ac0-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="21ac0-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<standardEndpoints >** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="21ac0-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="21ac0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<dynamicEndpoint >** ](dynamicendpoint.md)</span><span class="sxs-lookup"><span data-stu-id="21ac0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)</span></span>\
<span data-ttu-id="21ac0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<standardEndpoint >** </span><span class="sxs-lookup"><span data-stu-id="21ac0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**</span></span>\
<span data-ttu-id="21ac0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<discoveryClientSettings >** ](discoveryclientsettings.md)</span><span class="sxs-lookup"><span data-stu-id="21ac0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<discoveryClientSettings>**](discoveryclientsettings.md)</span></span>\
<span data-ttu-id="21ac0-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<findCriteria >**</span><span class="sxs-lookup"><span data-stu-id="21ac0-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<findCriteria>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21ac0-111">구문</span><span class="sxs-lookup"><span data-stu-id="21ac0-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="21ac0-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="21ac0-112">Attributes and Elements</span></span>  
 <span data-ttu-id="21ac0-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="21ac0-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="21ac0-114">특성</span><span class="sxs-lookup"><span data-stu-id="21ac0-114">Attributes</span></span>  
  
|<span data-ttu-id="21ac0-115">특성</span><span class="sxs-lookup"><span data-stu-id="21ac0-115">Attribute</span></span>|<span data-ttu-id="21ac0-116">Description</span><span class="sxs-lookup"><span data-stu-id="21ac0-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="21ac0-117">duration</span><span class="sxs-lookup"><span data-stu-id="21ac0-117">duration</span></span>|<span data-ttu-id="21ac0-118">네트워크에서 서비스로부터 응답을 기다리는 최대 시간을 지정하는 Timespan 값입니다.</span><span class="sxs-lookup"><span data-stu-id="21ac0-118">A Timespan value that specifies the maximum time to wait for replies from services on the network.</span></span> <span data-ttu-id="21ac0-119">기본 시간은 20초입니다.</span><span class="sxs-lookup"><span data-stu-id="21ac0-119">The default duration is 20 seconds.</span></span>|  
|<span data-ttu-id="21ac0-120">maxResults</span><span class="sxs-lookup"><span data-stu-id="21ac0-120">maxResults</span></span>|<span data-ttu-id="21ac0-121">네트워크 또는 인터넷에서 서비스로부터 기다리는 최대 응답 횟수를 지정하는 정수입니다</span><span class="sxs-lookup"><span data-stu-id="21ac0-121">An integer that specifies the maximum number of replies to wait for, from services on a network or the Internet.</span></span> <span data-ttu-id="21ac0-122">`duration` 특성에 지정된 시간이 경과되기 전에 최대 응답이 수신되는 경우 찾기 작업이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="21ac0-122">If maximum replies are received before the value specified in the `duration` attribute has elapsed, the find operation ends.</span></span>|  
|<span data-ttu-id="21ac0-123">scopeMatchBy</span><span class="sxs-lookup"><span data-stu-id="21ac0-123">scopeMatchBy</span></span>|<span data-ttu-id="21ac0-124">Probe 메시지의 범위와 엔드포인트의 범위를 일치시키는 동안 사용할 일치 알고리즘을 지정하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="21ac0-124">A URI that specify the matching algorithm to use while matching the scopes in the Probe message with that of the endpoint.</span></span><br /><br /> <span data-ttu-id="21ac0-125">다섯 가지의 범위 일치 규칙이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="21ac0-125">There are five supported scope-matching rules.</span></span> <span data-ttu-id="21ac0-126">범위 일치 규칙을 지정하지 않으면 `ScopeMatchByPrefix`가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="21ac0-126">If you do not specify a scope-matching rule, `ScopeMatchByPrefix` is used.</span></span> <span data-ttu-id="21ac0-127">이에 대한 자세한 내용은 <xref:System.ServiceModel.Discovery.FindCriteria>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="21ac0-127">For more information on this, see <xref:System.ServiceModel.Discovery.FindCriteria>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="21ac0-128">자식 요소</span><span class="sxs-lookup"><span data-stu-id="21ac0-128">Child Elements</span></span>  
  
|<span data-ttu-id="21ac0-129">요소</span><span class="sxs-lookup"><span data-stu-id="21ac0-129">Element</span></span>|<span data-ttu-id="21ac0-130">Description</span><span class="sxs-lookup"><span data-stu-id="21ac0-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="21ac0-131">\<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="21ac0-131">\<contractTypeNames></span></span>](contracttypenames.md)|<span data-ttu-id="21ac0-132">워크플로 서비스 계약 형식의 이름을 포함 하는 구성 요소 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="21ac0-132">A collection of configuration elements that contain the names of workflow service contract types.</span></span>|  
|<span data-ttu-id="21ac0-133">\<findcriteria의 \<확장 > ></span><span class="sxs-lookup"><span data-stu-id="21ac0-133">\<extensions> of \<findCriteria></span></span>|<span data-ttu-id="21ac0-134">확장을 제공하는 XML 요소 개체의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="21ac0-134">A collection of XML element objects that provide extensions.</span></span>|  
|[<span data-ttu-id="21ac0-135">\<scopes></span><span class="sxs-lookup"><span data-stu-id="21ac0-135">\<scopes></span></span>](scopes.md)|<span data-ttu-id="21ac0-136">찾기 작업 중에 특정 서비스를 찾기 위해 사용하는 절대 URI를 포함하는 개체의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="21ac0-136">A collection of objects that contain absolute URIs that are used during a find operation to locate a specific service or services.</span></span><br /><br /> <span data-ttu-id="21ac0-137">특정 서비스를 찾으면 서비스 URI와 범위 URI 간에 성공한 일치 항목이 생깁니다. 이때 경우에 따라 일치의 복잡한 문제를 처리하는 범위 규칙이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="21ac0-137">If the specific service is found, a successful match has been made between the service URI and the Scope URI, sometimes with the help of scope rules that handle complications of matching.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="21ac0-138">부모 요소</span><span class="sxs-lookup"><span data-stu-id="21ac0-138">Parent Elements</span></span>  
  
|<span data-ttu-id="21ac0-139">요소</span><span class="sxs-lookup"><span data-stu-id="21ac0-139">Element</span></span>|<span data-ttu-id="21ac0-140">Description</span><span class="sxs-lookup"><span data-stu-id="21ac0-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="21ac0-141">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="21ac0-141">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="21ac0-142">애플리케이션에서 서비스 검색 프로세스에 클라이언트로 참여하기 위해 필요한 설정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="21ac0-142">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="21ac0-143">참고자료</span><span class="sxs-lookup"><span data-stu-id="21ac0-143">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
