---
description: 다음에 대해 자세히 알아보세요. <discoveryClientSettings>
title: <discoveryClientSettings>
ms.date: 03/30/2017
ms.assetid: 02e1b823-a8bb-4074-90d5-8599f71e8f9d
ms.openlocfilehash: c2fda0dea33ffd6dbca24881eefab2e54e361f92
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802296"
---
# \<discoveryClientSettings>

<span data-ttu-id="45ce2-102">애플리케이션에서 서비스 검색 프로세스에 클라이언트로 참여하기 위해 필요한 설정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="45ce2-102">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryClientSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="45ce2-103">구문</span><span class="sxs-lookup"><span data-stu-id="45ce2-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="45ce2-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="45ce2-104">Attributes and Elements</span></span>  

 <span data-ttu-id="45ce2-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="45ce2-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="45ce2-106">특성</span><span class="sxs-lookup"><span data-stu-id="45ce2-106">Attributes</span></span>  
  
|<span data-ttu-id="45ce2-107">attribute</span><span class="sxs-lookup"><span data-stu-id="45ce2-107">Attribute</span></span>|<span data-ttu-id="45ce2-108">설명</span><span class="sxs-lookup"><span data-stu-id="45ce2-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="45ce2-109">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="45ce2-109">discoveryEndpoint</span></span>|<span data-ttu-id="45ce2-110">클라이언트 애플리케이션에서 런타임에 검색 가능한 서비스를 자동으로 검색하고 해당 주소를 찾을 수 있도록 하는 검색 엔드포인트의 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="45ce2-110">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="45ce2-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="45ce2-111">Child Elements</span></span>  
  
|<span data-ttu-id="45ce2-112">요소</span><span class="sxs-lookup"><span data-stu-id="45ce2-112">Element</span></span>|<span data-ttu-id="45ce2-113">설명</span><span class="sxs-lookup"><span data-stu-id="45ce2-113">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="45ce2-114">클라이언트 애플리케이션에서 검색 서비스를 찾기 위해 사용하는 조건 집합을 제공하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="45ce2-114">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="45ce2-115">기준을 검색 조건(찾으려는 서비스 지정) 및 찾기 종료 조건(검색 지속 기간)으로 그룹화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45ce2-115">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="45ce2-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="45ce2-116">Parent Elements</span></span>  
  
|<span data-ttu-id="45ce2-117">요소</span><span class="sxs-lookup"><span data-stu-id="45ce2-117">Element</span></span>|<span data-ttu-id="45ce2-118">설명</span><span class="sxs-lookup"><span data-stu-id="45ce2-118">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="45ce2-119">애플리케이션이 런타임에 엔드포인트 주소를 동적으로 찾을 수 있는 클라이언트 프로그램으로 기능하도록 설정하기 위한 정보를 포함하는 표준 엔드포인트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="45ce2-119">Defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="45ce2-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="45ce2-120">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientSettingsElement>
