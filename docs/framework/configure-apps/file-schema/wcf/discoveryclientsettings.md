---
title: <discoveryClientSettings>
ms.date: 03/30/2017
ms.assetid: 02e1b823-a8bb-4074-90d5-8599f71e8f9d
ms.openlocfilehash: 0b014a9d797ded61949a374486824ee3ebc34661
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59136255"
---
# <a name="discoveryclientsettings"></a><span data-ttu-id="eb410-101">\<discoveryClientSettings></span><span class="sxs-lookup"><span data-stu-id="eb410-101">\<discoveryClientSettings></span></span>
<span data-ttu-id="eb410-102">응용 프로그램에서 서비스 검색 프로세스에 클라이언트로 참여하기 위해 필요한 설정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb410-102">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>  
  
<span data-ttu-id="eb410-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="eb410-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="eb410-104">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="eb410-104">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb410-105">구문</span><span class="sxs-lookup"><span data-stu-id="eb410-105">Syntax</span></span>  
  
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
              <add scope="URI"/>
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb410-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="eb410-106">Attributes and Elements</span></span>  
 <span data-ttu-id="eb410-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eb410-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eb410-108">특성</span><span class="sxs-lookup"><span data-stu-id="eb410-108">Attributes</span></span>  
  
|<span data-ttu-id="eb410-109">특성</span><span class="sxs-lookup"><span data-stu-id="eb410-109">Attribute</span></span>|<span data-ttu-id="eb410-110">설명</span><span class="sxs-lookup"><span data-stu-id="eb410-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="eb410-111">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="eb410-111">discoveryEndpoint</span></span>|<span data-ttu-id="eb410-112">클라이언트 응용 프로그램에서 런타임에 검색 가능한 서비스를 자동으로 검색하고 해당 주소를 찾을 수 있도록 하는 검색 엔드포인트의 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="eb410-112">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eb410-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="eb410-113">Child Elements</span></span>  
  
|<span data-ttu-id="eb410-114">요소</span><span class="sxs-lookup"><span data-stu-id="eb410-114">Element</span></span>|<span data-ttu-id="eb410-115">설명</span><span class="sxs-lookup"><span data-stu-id="eb410-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eb410-116">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="eb410-116">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="eb410-117">클라이언트 응용 프로그램에서 검색 서비스를 찾기 위해 사용하는 조건 집합을 제공하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="eb410-117">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="eb410-118">조건 (찾으려는 서비스 지정) 하는 검색 조건으로 그룹화 할 수 있습니다 및 찾기 종료 조건 (검색 지속 기간).</span><span class="sxs-lookup"><span data-stu-id="eb410-118">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="eb410-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="eb410-119">Parent Elements</span></span>  
  
|<span data-ttu-id="eb410-120">요소</span><span class="sxs-lookup"><span data-stu-id="eb410-120">Element</span></span>|<span data-ttu-id="eb410-121">설명</span><span class="sxs-lookup"><span data-stu-id="eb410-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eb410-122">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="eb410-122">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="eb410-123">응용 프로그램이 런타임에 엔드포인트 주소를 동적으로 찾을 수 있는 클라이언트 프로그램으로 기능하도록 설정하기 위한 정보를 포함하는 표준 엔드포인트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="eb410-123">Defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eb410-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="eb410-124">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientSettingsElement>
