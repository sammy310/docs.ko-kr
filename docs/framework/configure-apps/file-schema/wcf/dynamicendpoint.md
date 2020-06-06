---
title: <dynamicEndpoint>
ms.date: 03/30/2017
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
ms.openlocfilehash: da57ca3ba3bc0036727a749f1cab9ec3657a4fda
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855349"
---
# \<dynamicEndpoint>
<span data-ttu-id="5f4c9-101">이 구성 요소는 애플리케이션이 런타임에 엔드포인트 주소를 동적으로 찾을 수 있는 클라이언트 프로그램으로 기능하도록 설정하기 위한 정보를 포함하는 표준 엔드포인트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5f4c9-101">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dynamicEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="5f4c9-102">구문</span><span class="sxs-lookup"><span data-stu-id="5f4c9-102">Syntax</span></span>  
  
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
              <add scope="URI" />
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5f4c9-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5f4c9-103">Attributes and Elements</span></span>  
 <span data-ttu-id="5f4c9-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5f4c9-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5f4c9-105">특성</span><span class="sxs-lookup"><span data-stu-id="5f4c9-105">Attributes</span></span>  
 <span data-ttu-id="5f4c9-106">없음</span><span class="sxs-lookup"><span data-stu-id="5f4c9-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5f4c9-107">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5f4c9-107">Child Elements</span></span>  
  
|<span data-ttu-id="5f4c9-108">요소</span><span class="sxs-lookup"><span data-stu-id="5f4c9-108">Element</span></span>|<span data-ttu-id="5f4c9-109">Description</span><span class="sxs-lookup"><span data-stu-id="5f4c9-109">Description</span></span>|  
|-------------|-----------------|  
|[\<discoveryClientSettings>](discoveryclientsettings.md)|<span data-ttu-id="5f4c9-110">애플리케이션에서 서비스 검색 프로세스에 클라이언트로 참여하기 위해 필요한 설정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f4c9-110">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5f4c9-111">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5f4c9-111">Parent Elements</span></span>  
  
|<span data-ttu-id="5f4c9-112">요소</span><span class="sxs-lookup"><span data-stu-id="5f4c9-112">Element</span></span>|<span data-ttu-id="5f4c9-113">Description</span><span class="sxs-lookup"><span data-stu-id="5f4c9-113">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="5f4c9-114">하나 이상의 속성(주소, 바인딩, 계약)이 고정된 미리 정의된 엔드포인트인 표준 엔드포인트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="5f4c9-114">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5f4c9-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5f4c9-115">See also</span></span>

- <xref:System.ServiceModel.Discovery.DynamicEndpoint>
- <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
