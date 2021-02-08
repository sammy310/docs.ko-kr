---
description: 다음에 대해 자세히 알아보세요. <scopes>
title: <scopes>
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: 2df1101beb5b1bc09c2d98eb89a8200303c5b456
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786865"
---
# \<scopes>

<span data-ttu-id="a8cf8-102">쿼리 중에 서비스 엔드포인트를 필터링하기 위해 사용할 수 있는 사용자 지정 범위 URI를 지정하는 구성 요소의 컬렉션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a8cf8-102">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointDiscovery>**](endpointdiscovery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<scopes>**  
  
## <a name="syntax"></a><span data-ttu-id="a8cf8-103">구문</span><span class="sxs-lookup"><span data-stu-id="a8cf8-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a8cf8-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a8cf8-104">Attributes and Elements</span></span>  

 <span data-ttu-id="a8cf8-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a8cf8-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a8cf8-106">특성</span><span class="sxs-lookup"><span data-stu-id="a8cf8-106">Attributes</span></span>  

 <span data-ttu-id="a8cf8-107">없음</span><span class="sxs-lookup"><span data-stu-id="a8cf8-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a8cf8-108">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a8cf8-108">Child Elements</span></span>  
  
|<span data-ttu-id="a8cf8-109">attribute</span><span class="sxs-lookup"><span data-stu-id="a8cf8-109">Attribute</span></span>|<span data-ttu-id="a8cf8-110">설명</span><span class="sxs-lookup"><span data-stu-id="a8cf8-110">Description</span></span>|  
|---------------|-----------------|  
|[\<add>](add-of-scopes.md)|<span data-ttu-id="a8cf8-111">서비스를 찾기 위한 일치 기준으로 사용할 수 있는 엔드포인트의 범위 정보를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a8cf8-111">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a8cf8-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a8cf8-112">Parent Elements</span></span>  
  
|<span data-ttu-id="a8cf8-113">요소</span><span class="sxs-lookup"><span data-stu-id="a8cf8-113">Element</span></span>|<span data-ttu-id="a8cf8-114">설명</span><span class="sxs-lookup"><span data-stu-id="a8cf8-114">Description</span></span>|  
|-------------|-----------------|  
|[\<endpointDiscovery>](endpointdiscovery.md)|<span data-ttu-id="a8cf8-115">검색 기능, 범위 및 해당 메타데이터에 대한 사용자 지정 확장 등 엔드포인트에 대한 다양한 검색 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a8cf8-115">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a8cf8-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a8cf8-116">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
