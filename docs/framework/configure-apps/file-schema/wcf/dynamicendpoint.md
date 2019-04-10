---
title: <dynamicEndpoint>
ms.date: 03/30/2017
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
ms.openlocfilehash: e1a53869faa1997d2e79c3d2869a15001ee29626
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59187748"
---
# <a name="dynamicendpoint"></a><span data-ttu-id="cbc47-101">\<dynamicEndpoint></span><span class="sxs-lookup"><span data-stu-id="cbc47-101">\<dynamicEndpoint></span></span>
<span data-ttu-id="cbc47-102">이 구성 요소는 응용 프로그램이 런타임에 엔드포인트 주소를 동적으로 찾을 수 있는 클라이언트 프로그램으로 기능하도록 설정하기 위한 정보를 포함하는 표준 엔드포인트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc47-102">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
<span data-ttu-id="cbc47-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="cbc47-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="cbc47-104">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="cbc47-104">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbc47-105">구문</span><span class="sxs-lookup"><span data-stu-id="cbc47-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cbc47-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="cbc47-106">Attributes and Elements</span></span>  
 <span data-ttu-id="cbc47-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc47-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cbc47-108">특성</span><span class="sxs-lookup"><span data-stu-id="cbc47-108">Attributes</span></span>  
 <span data-ttu-id="cbc47-109">없음</span><span class="sxs-lookup"><span data-stu-id="cbc47-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cbc47-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="cbc47-110">Child Elements</span></span>  
  
|<span data-ttu-id="cbc47-111">요소</span><span class="sxs-lookup"><span data-stu-id="cbc47-111">Element</span></span>|<span data-ttu-id="cbc47-112">설명</span><span class="sxs-lookup"><span data-stu-id="cbc47-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cbc47-113">\<discoveryClientSettings></span><span class="sxs-lookup"><span data-stu-id="cbc47-113">\<discoveryClientSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryclientsettings.md)|<span data-ttu-id="cbc47-114">응용 프로그램에서 서비스 검색 프로세스에 클라이언트로 참여하기 위해 필요한 설정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbc47-114">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cbc47-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="cbc47-115">Parent Elements</span></span>  
  
|<span data-ttu-id="cbc47-116">요소</span><span class="sxs-lookup"><span data-stu-id="cbc47-116">Element</span></span>|<span data-ttu-id="cbc47-117">설명</span><span class="sxs-lookup"><span data-stu-id="cbc47-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cbc47-118">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="cbc47-118">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="cbc47-119">하나 이상의 속성(주소, 바인딩, 계약)이 고정된 미리 정의된 엔드포인트인 표준 엔드포인트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="cbc47-119">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cbc47-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="cbc47-120">See also</span></span>

- <xref:System.ServiceModel.Discovery.DynamicEndpoint>
- <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
