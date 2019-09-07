---
title: <scopes>
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: 57e9e19025db5e1fa588f073fdf30de09837a25d
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399926"
---
# <a name="scopes"></a><span data-ttu-id="91b95-101">\<scopes></span><span class="sxs-lookup"><span data-stu-id="91b95-101">\<scopes></span></span>
<span data-ttu-id="91b95-102">쿼리 중에 서비스 엔드포인트를 필터링하기 위해 사용할 수 있는 사용자 지정 범위 URI를 지정하는 구성 요소의 컬렉션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="91b95-102">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="91b95-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="91b95-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="91b95-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="91b95-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="91b95-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="91b95-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="91b95-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="91b95-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="91b95-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="91b95-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="91b95-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointDiscovery >** ](endpointdiscovery.md)</span><span class="sxs-lookup"><span data-stu-id="91b95-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointDiscovery>**](endpointdiscovery.md)</span></span>\
<span data-ttu-id="91b95-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<범위 >**</span><span class="sxs-lookup"><span data-stu-id="91b95-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<scopes>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91b95-110">구문</span><span class="sxs-lookup"><span data-stu-id="91b95-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91b95-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="91b95-111">Attributes and Elements</span></span>  
 <span data-ttu-id="91b95-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="91b95-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91b95-113">특성</span><span class="sxs-lookup"><span data-stu-id="91b95-113">Attributes</span></span>  
 <span data-ttu-id="91b95-114">없음</span><span class="sxs-lookup"><span data-stu-id="91b95-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="91b95-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="91b95-115">Child Elements</span></span>  
  
|<span data-ttu-id="91b95-116">특성</span><span class="sxs-lookup"><span data-stu-id="91b95-116">Attribute</span></span>|<span data-ttu-id="91b95-117">설명</span><span class="sxs-lookup"><span data-stu-id="91b95-117">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="91b95-118">\<add></span><span class="sxs-lookup"><span data-stu-id="91b95-118">\<add></span></span>](add-of-scopes.md)|<span data-ttu-id="91b95-119">서비스를 찾기 위한 일치 기준으로 사용할 수 있는 엔드포인트의 범위 정보를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="91b95-119">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="91b95-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="91b95-120">Parent Elements</span></span>  
  
|<span data-ttu-id="91b95-121">요소</span><span class="sxs-lookup"><span data-stu-id="91b95-121">Element</span></span>|<span data-ttu-id="91b95-122">Description</span><span class="sxs-lookup"><span data-stu-id="91b95-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="91b95-123">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="91b95-123">\<endpointDiscovery></span></span>](endpointdiscovery.md)|<span data-ttu-id="91b95-124">검색 기능, 범위 및 해당 메타데이터에 대한 사용자 지정 확장 등 엔드포인트에 대한 다양한 검색 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="91b95-124">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="91b95-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="91b95-125">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
