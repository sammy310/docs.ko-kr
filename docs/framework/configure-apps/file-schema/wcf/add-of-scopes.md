---
title: <scopes>의 <add>
ms.date: 03/30/2017
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
ms.openlocfilehash: bcde6b18c34dccf1716c809dddeb45b1b4da90f0
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398302"
---
# <a name="add-of-scopes"></a><span data-ttu-id="ca3e3-102">\<\<범위 > 추가 ></span><span class="sxs-lookup"><span data-stu-id="ca3e3-102">\<add> of \<scopes></span></span>
<span data-ttu-id="ca3e3-103">쿼리 중에 서비스 엔드포인트를 필터링하기 위해 사용할 수 있는 사용자 지정 범위 URI를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ca3e3-103">Adds a custom scope Uri that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="ca3e3-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ca3e3-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ca3e3-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ca3e3-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ca3e3-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="ca3e3-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="ca3e3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="ca3e3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="ca3e3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="ca3e3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="ca3e3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointDiscovery >** ](endpointdiscovery.md)</span><span class="sxs-lookup"><span data-stu-id="ca3e3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointDiscovery>**](endpointdiscovery.md)</span></span>\
<span data-ttu-id="ca3e3-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<범위 >** ](scopes.md)</span><span class="sxs-lookup"><span data-stu-id="ca3e3-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<scopes>**](scopes.md)</span></span>\
<span data-ttu-id="ca3e3-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> 추가**</span><span class="sxs-lookup"><span data-stu-id="ca3e3-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca3e3-112">구문</span><span class="sxs-lookup"><span data-stu-id="ca3e3-112">Syntax</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enable="Boolean">
        <scopes>
          <add scope="URI" />
        </scopes>
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ca3e3-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ca3e3-113">Attributes and Elements</span></span>  
 <span data-ttu-id="ca3e3-114">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ca3e3-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ca3e3-115">특성</span><span class="sxs-lookup"><span data-stu-id="ca3e3-115">Attributes</span></span>  
  
|<span data-ttu-id="ca3e3-116">특성</span><span class="sxs-lookup"><span data-stu-id="ca3e3-116">Attribute</span></span>|<span data-ttu-id="ca3e3-117">설명</span><span class="sxs-lookup"><span data-stu-id="ca3e3-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ca3e3-118">범위</span><span class="sxs-lookup"><span data-stu-id="ca3e3-118">scope</span></span>|<span data-ttu-id="ca3e3-119">서비스를 찾기 위한 일치 기준으로 사용할 수 있는 엔드포인트의 범위 정보가 포함되는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="ca3e3-119">A URI that contains scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ca3e3-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ca3e3-120">Child Elements</span></span>  
 <span data-ttu-id="ca3e3-121">없음</span><span class="sxs-lookup"><span data-stu-id="ca3e3-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ca3e3-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ca3e3-122">Parent Elements</span></span>  
  
|<span data-ttu-id="ca3e3-123">요소</span><span class="sxs-lookup"><span data-stu-id="ca3e3-123">Element</span></span>|<span data-ttu-id="ca3e3-124">설명</span><span class="sxs-lookup"><span data-stu-id="ca3e3-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ca3e3-125">\<scopes></span><span class="sxs-lookup"><span data-stu-id="ca3e3-125">\<scopes></span></span>](scopes.md)|<span data-ttu-id="ca3e3-126">쿼리 중에 서비스 엔드포인트를 필터링하기 위해 사용할 수 있는 사용자 지정 범위 URI를 지정하는 구성 요소의 컬렉션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ca3e3-126">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ca3e3-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="ca3e3-127">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
