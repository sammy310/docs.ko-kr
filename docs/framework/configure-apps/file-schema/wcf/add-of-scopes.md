---
title: <scopes>의 <add>
ms.date: 03/30/2017
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
ms.openlocfilehash: bcde6b18c34dccf1716c809dddeb45b1b4da90f0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398302"
---
# <a name="add-of-scopes"></a><span data-ttu-id="01932-102">\<scopes>의 \<add></span><span class="sxs-lookup"><span data-stu-id="01932-102">\<add> of \<scopes></span></span>
<span data-ttu-id="01932-103">쿼리 중에 서비스 엔드포인트를 필터링하기 위해 사용할 수 있는 사용자 지정 범위 URI를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="01932-103">Adds a custom scope Uri that can be used to filter service endpoints during query.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointDiscovery>**](endpointdiscovery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<scopes>**](scopes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="01932-104">구문</span><span class="sxs-lookup"><span data-stu-id="01932-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="01932-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="01932-105">Attributes and Elements</span></span>  
 <span data-ttu-id="01932-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="01932-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="01932-107">특성</span><span class="sxs-lookup"><span data-stu-id="01932-107">Attributes</span></span>  
  
|<span data-ttu-id="01932-108">attribute</span><span class="sxs-lookup"><span data-stu-id="01932-108">Attribute</span></span>|<span data-ttu-id="01932-109">Description</span><span class="sxs-lookup"><span data-stu-id="01932-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="01932-110">scope</span><span class="sxs-lookup"><span data-stu-id="01932-110">scope</span></span>|<span data-ttu-id="01932-111">서비스를 찾기 위한 일치 기준으로 사용할 수 있는 엔드포인트의 범위 정보가 포함되는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="01932-111">A URI that contains scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="01932-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="01932-112">Child Elements</span></span>  
 <span data-ttu-id="01932-113">없음</span><span class="sxs-lookup"><span data-stu-id="01932-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="01932-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="01932-114">Parent Elements</span></span>  
  
|<span data-ttu-id="01932-115">요소</span><span class="sxs-lookup"><span data-stu-id="01932-115">Element</span></span>|<span data-ttu-id="01932-116">Description</span><span class="sxs-lookup"><span data-stu-id="01932-116">Description</span></span>|  
|-------------|-----------------|  
|[\<scopes>](scopes.md)|<span data-ttu-id="01932-117">쿼리 중에 서비스 엔드포인트를 필터링하기 위해 사용할 수 있는 사용자 지정 범위 URI를 지정하는 구성 요소의 컬렉션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="01932-117">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="01932-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="01932-118">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
