---
description: 다음에 대해 자세히 알아보세요. <discoveryClient>
title: <discoveryClient>
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: d04eee828bb16e56a65c39059665feb745f3006a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754396"
---
# \<discoveryClient>

<span data-ttu-id="6bbc0-102">클라이언트 애플리케이션에서 런타임에 검색 가능 서비스를 자동으로 검색하고 해당 주소를 찾을 수 있도록 하는 사용자 지정 바인딩을 만들기 위한 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6bbc0-102">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryClient>**  
  
## <a name="syntax"></a><span data-ttu-id="6bbc0-103">구문</span><span class="sxs-lookup"><span data-stu-id="6bbc0-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6bbc0-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="6bbc0-104">Attributes and Elements</span></span>  

 <span data-ttu-id="6bbc0-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6bbc0-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6bbc0-106">특성</span><span class="sxs-lookup"><span data-stu-id="6bbc0-106">Attributes</span></span>  
  
|<span data-ttu-id="6bbc0-107">attribute</span><span class="sxs-lookup"><span data-stu-id="6bbc0-107">Attribute</span></span>|<span data-ttu-id="6bbc0-108">설명</span><span class="sxs-lookup"><span data-stu-id="6bbc0-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6bbc0-109">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="6bbc0-109">discoveryEndpoint</span></span>|<span data-ttu-id="6bbc0-110">클라이언트 애플리케이션에서 런타임에 검색 가능한 서비스를 자동으로 검색하고 해당 주소를 찾을 수 있도록 하는 검색 엔드포인트의 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="6bbc0-110">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6bbc0-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6bbc0-111">Child Elements</span></span>  
  
|<span data-ttu-id="6bbc0-112">요소</span><span class="sxs-lookup"><span data-stu-id="6bbc0-112">Element</span></span>|<span data-ttu-id="6bbc0-113">설명</span><span class="sxs-lookup"><span data-stu-id="6bbc0-113">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="6bbc0-114">클라이언트 애플리케이션에서 검색 서비스를 찾기 위해 사용하는 조건 집합을 제공하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6bbc0-114">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="6bbc0-115">기준을 검색 조건(찾으려는 서비스 지정) 및 찾기 종료 조건(검색 지속 기간)으로 그룹화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bbc0-115">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6bbc0-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6bbc0-116">Parent Elements</span></span>  
  
|<span data-ttu-id="6bbc0-117">요소</span><span class="sxs-lookup"><span data-stu-id="6bbc0-117">Element</span></span>|<span data-ttu-id="6bbc0-118">설명</span><span class="sxs-lookup"><span data-stu-id="6bbc0-118">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="6bbc0-119">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6bbc0-119">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6bbc0-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6bbc0-120">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
