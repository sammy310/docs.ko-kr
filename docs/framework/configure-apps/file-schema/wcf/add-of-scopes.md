---
title: <scopes>의 <add>
ms.date: 03/30/2017
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
ms.openlocfilehash: 1f5b5ea621614880286181c7584863ea024b3d04
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149012"
---
# <a name="add-of-scopes"></a><span data-ttu-id="9d42d-102">\<scopes>의 \<add></span><span class="sxs-lookup"><span data-stu-id="9d42d-102">\<add> of \<scopes></span></span>

<span data-ttu-id="9d42d-103">쿼리 중에 서비스 엔드포인트를 필터링하기 위해 사용할 수 있는 사용자 지정 범위 URI를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9d42d-103">Adds a custom scope Uri that can be used to filter service endpoints during query.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointDiscovery>**](endpointdiscovery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<scopes>**](scopes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="9d42d-104">구문</span><span class="sxs-lookup"><span data-stu-id="9d42d-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9d42d-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9d42d-105">Attributes and Elements</span></span>  

 <span data-ttu-id="9d42d-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9d42d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9d42d-107">특성</span><span class="sxs-lookup"><span data-stu-id="9d42d-107">Attributes</span></span>  
  
|<span data-ttu-id="9d42d-108">attribute</span><span class="sxs-lookup"><span data-stu-id="9d42d-108">Attribute</span></span>|<span data-ttu-id="9d42d-109">설명</span><span class="sxs-lookup"><span data-stu-id="9d42d-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9d42d-110">scope</span><span class="sxs-lookup"><span data-stu-id="9d42d-110">scope</span></span>|<span data-ttu-id="9d42d-111">서비스를 찾기 위한 일치 기준으로 사용할 수 있는 엔드포인트의 범위 정보가 포함되는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="9d42d-111">A URI that contains scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9d42d-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9d42d-112">Child Elements</span></span>  

 <span data-ttu-id="9d42d-113">없음</span><span class="sxs-lookup"><span data-stu-id="9d42d-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9d42d-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9d42d-114">Parent Elements</span></span>  
  
|<span data-ttu-id="9d42d-115">요소</span><span class="sxs-lookup"><span data-stu-id="9d42d-115">Element</span></span>|<span data-ttu-id="9d42d-116">설명</span><span class="sxs-lookup"><span data-stu-id="9d42d-116">Description</span></span>|  
|-------------|-----------------|  
|[\<scopes>](scopes.md)|<span data-ttu-id="9d42d-117">쿼리 중에 서비스 엔드포인트를 필터링하기 위해 사용할 수 있는 사용자 지정 범위 URI를 지정하는 구성 요소의 컬렉션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9d42d-117">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9d42d-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9d42d-118">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
