---
title: <discoveryClientSettings>
ms.date: 03/30/2017
ms.assetid: 02e1b823-a8bb-4074-90d5-8599f71e8f9d
ms.openlocfilehash: 929c5d170bfc27160e3e15b8bd2f9f26e0ed8975
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855404"
---
# <a name="discoveryclientsettings"></a><span data-ttu-id="c04f8-101">\<discoveryClientSettings></span><span class="sxs-lookup"><span data-stu-id="c04f8-101">\<discoveryClientSettings></span></span>
<span data-ttu-id="c04f8-102">애플리케이션에서 서비스 검색 프로세스에 클라이언트로 참여하기 위해 필요한 설정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c04f8-102">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>  
  
<span data-ttu-id="c04f8-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c04f8-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c04f8-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c04f8-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c04f8-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<standardEndpoints >** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="c04f8-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="c04f8-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<dynamicEndpoint >** ](dynamicendpoint.md)</span><span class="sxs-lookup"><span data-stu-id="c04f8-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)</span></span>\
<span data-ttu-id="c04f8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<standardEndpoint >** </span><span class="sxs-lookup"><span data-stu-id="c04f8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**</span></span>\
<span data-ttu-id="c04f8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<discoveryClientSettings >**</span><span class="sxs-lookup"><span data-stu-id="c04f8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryClientSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c04f8-109">구문</span><span class="sxs-lookup"><span data-stu-id="c04f8-109">Syntax</span></span>  
  
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
            <contractTypeNames>
            <extensions />
            <scopes>
              <add scope="URI"/>
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c04f8-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c04f8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c04f8-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c04f8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c04f8-112">특성</span><span class="sxs-lookup"><span data-stu-id="c04f8-112">Attributes</span></span>  
  
|<span data-ttu-id="c04f8-113">특성</span><span class="sxs-lookup"><span data-stu-id="c04f8-113">Attribute</span></span>|<span data-ttu-id="c04f8-114">Description</span><span class="sxs-lookup"><span data-stu-id="c04f8-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c04f8-115">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="c04f8-115">discoveryEndpoint</span></span>|<span data-ttu-id="c04f8-116">클라이언트 애플리케이션에서 런타임에 검색 가능한 서비스를 자동으로 검색하고 해당 주소를 찾을 수 있도록 하는 검색 엔드포인트의 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c04f8-116">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c04f8-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c04f8-117">Child Elements</span></span>  
  
|<span data-ttu-id="c04f8-118">요소</span><span class="sxs-lookup"><span data-stu-id="c04f8-118">Element</span></span>|<span data-ttu-id="c04f8-119">Description</span><span class="sxs-lookup"><span data-stu-id="c04f8-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c04f8-120">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="c04f8-120">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="c04f8-121">클라이언트 애플리케이션에서 검색 서비스를 찾기 위해 사용하는 조건 집합을 제공하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="c04f8-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="c04f8-122">기준은 검색 조건 (찾으려는 서비스 지정)으로 그룹화 하 고 종료 조건 (검색이 마지막으로 수행 되는 시간)을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c04f8-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c04f8-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c04f8-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c04f8-124">요소</span><span class="sxs-lookup"><span data-stu-id="c04f8-124">Element</span></span>|<span data-ttu-id="c04f8-125">설명</span><span class="sxs-lookup"><span data-stu-id="c04f8-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c04f8-126">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="c04f8-126">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="c04f8-127">애플리케이션이 런타임에 엔드포인트 주소를 동적으로 찾을 수 있는 클라이언트 프로그램으로 기능하도록 설정하기 위한 정보를 포함하는 표준 엔드포인트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c04f8-127">Defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c04f8-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="c04f8-128">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientSettingsElement>
