---
description: 다음에 대해 자세히 알아보세요. <dynamicEndpoint>
title: <dynamicEndpoint>
ms.date: 03/30/2017
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
ms.openlocfilehash: 0fe30492e1daeecca5e27aef844f5f6977396049
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725898"
---
# \<dynamicEndpoint>

<span data-ttu-id="00e40-102">이 구성 요소는 애플리케이션이 런타임에 엔드포인트 주소를 동적으로 찾을 수 있는 클라이언트 프로그램으로 기능하도록 설정하기 위한 정보를 포함하는 표준 엔드포인트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="00e40-102">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dynamicEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="00e40-103">구문</span><span class="sxs-lookup"><span data-stu-id="00e40-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="00e40-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="00e40-104">Attributes and Elements</span></span>  

 <span data-ttu-id="00e40-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00e40-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="00e40-106">특성</span><span class="sxs-lookup"><span data-stu-id="00e40-106">Attributes</span></span>  

 <span data-ttu-id="00e40-107">없음</span><span class="sxs-lookup"><span data-stu-id="00e40-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="00e40-108">자식 요소</span><span class="sxs-lookup"><span data-stu-id="00e40-108">Child Elements</span></span>  
  
|<span data-ttu-id="00e40-109">요소</span><span class="sxs-lookup"><span data-stu-id="00e40-109">Element</span></span>|<span data-ttu-id="00e40-110">설명</span><span class="sxs-lookup"><span data-stu-id="00e40-110">Description</span></span>|  
|-------------|-----------------|  
|[\<discoveryClientSettings>](discoveryclientsettings.md)|<span data-ttu-id="00e40-111">애플리케이션에서 서비스 검색 프로세스에 클라이언트로 참여하기 위해 필요한 설정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="00e40-111">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="00e40-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="00e40-112">Parent Elements</span></span>  
  
|<span data-ttu-id="00e40-113">요소</span><span class="sxs-lookup"><span data-stu-id="00e40-113">Element</span></span>|<span data-ttu-id="00e40-114">설명</span><span class="sxs-lookup"><span data-stu-id="00e40-114">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="00e40-115">하나 이상의 속성(주소, 바인딩, 계약)이 고정된 미리 정의된 엔드포인트인 표준 엔드포인트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="00e40-115">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="00e40-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="00e40-116">See also</span></span>

- <xref:System.ServiceModel.Discovery.DynamicEndpoint>
- <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
