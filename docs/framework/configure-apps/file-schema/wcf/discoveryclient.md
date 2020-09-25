---
title: <discoveryClient>
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: af9cf127652f1e12ae57948f9b4a6a26285af793
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192258"
---
# \<discoveryClient>

<span data-ttu-id="7783f-101">클라이언트 애플리케이션에서 런타임에 검색 가능 서비스를 자동으로 검색하고 해당 주소를 찾을 수 있도록 하는 사용자 지정 바인딩을 만들기 위한 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7783f-101">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryClient>**  
  
## <a name="syntax"></a><span data-ttu-id="7783f-102">구문</span><span class="sxs-lookup"><span data-stu-id="7783f-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7783f-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7783f-103">Attributes and Elements</span></span>  

 <span data-ttu-id="7783f-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7783f-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7783f-105">특성</span><span class="sxs-lookup"><span data-stu-id="7783f-105">Attributes</span></span>  
  
|<span data-ttu-id="7783f-106">attribute</span><span class="sxs-lookup"><span data-stu-id="7783f-106">Attribute</span></span>|<span data-ttu-id="7783f-107">설명</span><span class="sxs-lookup"><span data-stu-id="7783f-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7783f-108">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="7783f-108">discoveryEndpoint</span></span>|<span data-ttu-id="7783f-109">클라이언트 애플리케이션에서 런타임에 검색 가능한 서비스를 자동으로 검색하고 해당 주소를 찾을 수 있도록 하는 검색 엔드포인트의 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7783f-109">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7783f-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7783f-110">Child Elements</span></span>  
  
|<span data-ttu-id="7783f-111">요소</span><span class="sxs-lookup"><span data-stu-id="7783f-111">Element</span></span>|<span data-ttu-id="7783f-112">설명</span><span class="sxs-lookup"><span data-stu-id="7783f-112">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="7783f-113">클라이언트 애플리케이션에서 검색 서비스를 찾기 위해 사용하는 조건 집합을 제공하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7783f-113">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="7783f-114">기준을 검색 조건(찾으려는 서비스 지정) 및 찾기 종료 조건(검색 지속 기간)으로 그룹화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7783f-114">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7783f-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7783f-115">Parent Elements</span></span>  
  
|<span data-ttu-id="7783f-116">요소</span><span class="sxs-lookup"><span data-stu-id="7783f-116">Element</span></span>|<span data-ttu-id="7783f-117">설명</span><span class="sxs-lookup"><span data-stu-id="7783f-117">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="7783f-118">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7783f-118">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7783f-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7783f-119">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
