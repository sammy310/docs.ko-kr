---
title: <discoveryClientSettings>
ms.date: 03/30/2017
ms.assetid: 02e1b823-a8bb-4074-90d5-8599f71e8f9d
ms.openlocfilehash: 6e3f273af807eb362f005fef63246013ecc88581
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192245"
---
# \<discoveryClientSettings>

<span data-ttu-id="2ad87-101">애플리케이션에서 서비스 검색 프로세스에 클라이언트로 참여하기 위해 필요한 설정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ad87-101">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryClientSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="2ad87-102">구문</span><span class="sxs-lookup"><span data-stu-id="2ad87-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2ad87-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2ad87-103">Attributes and Elements</span></span>  

 <span data-ttu-id="2ad87-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2ad87-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2ad87-105">특성</span><span class="sxs-lookup"><span data-stu-id="2ad87-105">Attributes</span></span>  
  
|<span data-ttu-id="2ad87-106">attribute</span><span class="sxs-lookup"><span data-stu-id="2ad87-106">Attribute</span></span>|<span data-ttu-id="2ad87-107">설명</span><span class="sxs-lookup"><span data-stu-id="2ad87-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2ad87-108">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="2ad87-108">discoveryEndpoint</span></span>|<span data-ttu-id="2ad87-109">클라이언트 애플리케이션에서 런타임에 검색 가능한 서비스를 자동으로 검색하고 해당 주소를 찾을 수 있도록 하는 검색 엔드포인트의 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2ad87-109">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2ad87-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2ad87-110">Child Elements</span></span>  
  
|<span data-ttu-id="2ad87-111">요소</span><span class="sxs-lookup"><span data-stu-id="2ad87-111">Element</span></span>|<span data-ttu-id="2ad87-112">설명</span><span class="sxs-lookup"><span data-stu-id="2ad87-112">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="2ad87-113">클라이언트 애플리케이션에서 검색 서비스를 찾기 위해 사용하는 조건 집합을 제공하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2ad87-113">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="2ad87-114">기준을 검색 조건(찾으려는 서비스 지정) 및 찾기 종료 조건(검색 지속 기간)으로 그룹화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ad87-114">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2ad87-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2ad87-115">Parent Elements</span></span>  
  
|<span data-ttu-id="2ad87-116">요소</span><span class="sxs-lookup"><span data-stu-id="2ad87-116">Element</span></span>|<span data-ttu-id="2ad87-117">설명</span><span class="sxs-lookup"><span data-stu-id="2ad87-117">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="2ad87-118">애플리케이션이 런타임에 엔드포인트 주소를 동적으로 찾을 수 있는 클라이언트 프로그램으로 기능하도록 설정하기 위한 정보를 포함하는 표준 엔드포인트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2ad87-118">Defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2ad87-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2ad87-119">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientSettingsElement>
