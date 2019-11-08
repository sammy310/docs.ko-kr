---
title: <discoveryClient>
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: 71305720cad0206ec3dabb1863e2f1cd72eb85f0
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73739038"
---
# <a name="discoveryclient"></a><span data-ttu-id="b19d2-101">\<discoveryClient ></span><span class="sxs-lookup"><span data-stu-id="b19d2-101">\<discoveryClient></span></span>
<span data-ttu-id="b19d2-102">클라이언트 애플리케이션에서 런타임에 검색 가능 서비스를 자동으로 검색하고 해당 주소를 찾을 수 있도록 하는 사용자 지정 바인딩을 만들기 위한 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b19d2-102">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
<span data-ttu-id="b19d2-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b19d2-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b19d2-104">[ **\<system serviceModel >** ](system-servicemodel.md) &nbsp; &nbsp; </span><span class="sxs-lookup"><span data-stu-id="b19d2-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="b19d2-105">&nbsp;&nbsp;&nbsp;&nbsp;\<[**바인딩**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="b19d2-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="b19d2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="b19d2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="b19d2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="b19d2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="b19d2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**discoveryClient >**</span><span class="sxs-lookup"><span data-stu-id="b19d2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryClient>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b19d2-109">구문</span><span class="sxs-lookup"><span data-stu-id="b19d2-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b19d2-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b19d2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b19d2-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b19d2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b19d2-112">특성</span><span class="sxs-lookup"><span data-stu-id="b19d2-112">Attributes</span></span>  
  
|<span data-ttu-id="b19d2-113">특성</span><span class="sxs-lookup"><span data-stu-id="b19d2-113">Attribute</span></span>|<span data-ttu-id="b19d2-114">설명</span><span class="sxs-lookup"><span data-stu-id="b19d2-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b19d2-115">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="b19d2-115">discoveryEndpoint</span></span>|<span data-ttu-id="b19d2-116">클라이언트 애플리케이션에서 런타임에 검색 가능한 서비스를 자동으로 검색하고 해당 주소를 찾을 수 있도록 하는 검색 엔드포인트의 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b19d2-116">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b19d2-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b19d2-117">Child Elements</span></span>  
  
|<span data-ttu-id="b19d2-118">요소</span><span class="sxs-lookup"><span data-stu-id="b19d2-118">Element</span></span>|<span data-ttu-id="b19d2-119">설명</span><span class="sxs-lookup"><span data-stu-id="b19d2-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b19d2-120">standardEndpoints를 \<</span><span class="sxs-lookup"><span data-stu-id="b19d2-120">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="b19d2-121">클라이언트 애플리케이션에서 검색 서비스를 찾기 위해 사용하는 조건 집합을 제공하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b19d2-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="b19d2-122">기준은 검색 조건 (찾으려는 서비스 지정)으로 그룹화 하 고 종료 조건 (검색이 마지막으로 수행 되는 시간)을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b19d2-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b19d2-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b19d2-123">Parent Elements</span></span>  
  
|<span data-ttu-id="b19d2-124">요소</span><span class="sxs-lookup"><span data-stu-id="b19d2-124">Element</span></span>|<span data-ttu-id="b19d2-125">설명</span><span class="sxs-lookup"><span data-stu-id="b19d2-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b19d2-126">\<binding ></span><span class="sxs-lookup"><span data-stu-id="b19d2-126">\<binding></span></span>](bindings.md)|<span data-ttu-id="b19d2-127">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b19d2-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b19d2-128">참조</span><span class="sxs-lookup"><span data-stu-id="b19d2-128">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
