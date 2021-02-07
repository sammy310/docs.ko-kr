---
description: '다음에 대 한 자세한 정보:: <add><scopes>'
title: <scopes>의 <add>
ms.date: 03/30/2017
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
ms.openlocfilehash: e5582a7599c221e9ac00e03178911290e18ff536
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99750236"
---
# <a name="add-of-scopes"></a><span data-ttu-id="acfb9-103">\<scopes>의 \<add></span><span class="sxs-lookup"><span data-stu-id="acfb9-103">\<add> of \<scopes></span></span>

<span data-ttu-id="acfb9-104">쿼리 중에 서비스 엔드포인트를 필터링하기 위해 사용할 수 있는 사용자 지정 범위 URI를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="acfb9-104">Adds a custom scope Uri that can be used to filter service endpoints during query.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointDiscovery>**](endpointdiscovery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<scopes>**](scopes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="acfb9-105">구문</span><span class="sxs-lookup"><span data-stu-id="acfb9-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="acfb9-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="acfb9-106">Attributes and Elements</span></span>  

 <span data-ttu-id="acfb9-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="acfb9-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="acfb9-108">특성</span><span class="sxs-lookup"><span data-stu-id="acfb9-108">Attributes</span></span>  
  
|<span data-ttu-id="acfb9-109">attribute</span><span class="sxs-lookup"><span data-stu-id="acfb9-109">Attribute</span></span>|<span data-ttu-id="acfb9-110">설명</span><span class="sxs-lookup"><span data-stu-id="acfb9-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="acfb9-111">scope</span><span class="sxs-lookup"><span data-stu-id="acfb9-111">scope</span></span>|<span data-ttu-id="acfb9-112">서비스를 찾기 위한 일치 기준으로 사용할 수 있는 엔드포인트의 범위 정보가 포함되는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="acfb9-112">A URI that contains scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="acfb9-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="acfb9-113">Child Elements</span></span>  

 <span data-ttu-id="acfb9-114">없음</span><span class="sxs-lookup"><span data-stu-id="acfb9-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="acfb9-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="acfb9-115">Parent Elements</span></span>  
  
|<span data-ttu-id="acfb9-116">요소</span><span class="sxs-lookup"><span data-stu-id="acfb9-116">Element</span></span>|<span data-ttu-id="acfb9-117">설명</span><span class="sxs-lookup"><span data-stu-id="acfb9-117">Description</span></span>|  
|-------------|-----------------|  
|[\<scopes>](scopes.md)|<span data-ttu-id="acfb9-118">쿼리 중에 서비스 엔드포인트를 필터링하기 위해 사용할 수 있는 사용자 지정 범위 URI를 지정하는 구성 요소의 컬렉션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="acfb9-118">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="acfb9-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="acfb9-119">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
