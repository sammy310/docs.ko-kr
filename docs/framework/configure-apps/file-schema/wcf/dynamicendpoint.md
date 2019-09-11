---
title: <dynamicEndpoint>
ms.date: 03/30/2017
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
ms.openlocfilehash: da57ca3ba3bc0036727a749f1cab9ec3657a4fda
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855349"
---
# <a name="dynamicendpoint"></a><span data-ttu-id="9f74e-101">\<dynamicEndpoint></span><span class="sxs-lookup"><span data-stu-id="9f74e-101">\<dynamicEndpoint></span></span>
<span data-ttu-id="9f74e-102">이 구성 요소는 애플리케이션이 런타임에 엔드포인트 주소를 동적으로 찾을 수 있는 클라이언트 프로그램으로 기능하도록 설정하기 위한 정보를 포함하는 표준 엔드포인트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9f74e-102">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
<span data-ttu-id="9f74e-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9f74e-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9f74e-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="9f74e-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9f74e-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<standardEndpoints >** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="9f74e-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="9f74e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<dynamicEndpoint >**</span><span class="sxs-lookup"><span data-stu-id="9f74e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dynamicEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f74e-107">구문</span><span class="sxs-lookup"><span data-stu-id="9f74e-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9f74e-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9f74e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9f74e-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9f74e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9f74e-110">특성</span><span class="sxs-lookup"><span data-stu-id="9f74e-110">Attributes</span></span>  
 <span data-ttu-id="9f74e-111">없음</span><span class="sxs-lookup"><span data-stu-id="9f74e-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9f74e-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9f74e-112">Child Elements</span></span>  
  
|<span data-ttu-id="9f74e-113">요소</span><span class="sxs-lookup"><span data-stu-id="9f74e-113">Element</span></span>|<span data-ttu-id="9f74e-114">Description</span><span class="sxs-lookup"><span data-stu-id="9f74e-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9f74e-115">\<discoveryClientSettings></span><span class="sxs-lookup"><span data-stu-id="9f74e-115">\<discoveryClientSettings></span></span>](discoveryclientsettings.md)|<span data-ttu-id="9f74e-116">애플리케이션에서 서비스 검색 프로세스에 클라이언트로 참여하기 위해 필요한 설정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f74e-116">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9f74e-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9f74e-117">Parent Elements</span></span>  
  
|<span data-ttu-id="9f74e-118">요소</span><span class="sxs-lookup"><span data-stu-id="9f74e-118">Element</span></span>|<span data-ttu-id="9f74e-119">Description</span><span class="sxs-lookup"><span data-stu-id="9f74e-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9f74e-120">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="9f74e-120">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="9f74e-121">하나 이상의 속성(주소, 바인딩, 계약)이 고정된 미리 정의된 엔드포인트인 표준 엔드포인트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="9f74e-121">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9f74e-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="9f74e-122">See also</span></span>

- <xref:System.ServiceModel.Discovery.DynamicEndpoint>
- <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
