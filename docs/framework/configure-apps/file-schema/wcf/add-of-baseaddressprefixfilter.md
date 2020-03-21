---
title: <baseAddressPrefixFilter>의 <add>
ms.date: 03/30/2017
ms.assetid: b226bede-8459-4de9-b2ac-3d39604ce2bc
ms.openlocfilehash: 8fdae02b558708a9b3f4535123752dce12dd5cf5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153142"
---
# <a name="add-of-baseaddressprefixfilter"></a><span data-ttu-id="400fd-102">\<\<베이스주소사전필터>> 추가</span><span class="sxs-lookup"><span data-stu-id="400fd-102">\<add> of \<baseAddressPrefixFilter></span></span>
<span data-ttu-id="400fd-103">IIS에서 WCF(Windows 통신 Foundation) 응용 프로그램을 호스팅할 때 적절한 IIS(인터넷 정보 서비스) 바인딩을 선택하는 메커니즘을 제공하는 통과 필터를 지정하는 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="400fd-103">Represents a configuration element that specifies a pass-through filter, which provides a mechanism to pick the appropriate Internet Information Services (IIS) bindings when hosting a Windows Communication Foundation (WCF) application in IIS.</span></span>  
  
<span data-ttu-id="400fd-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="400fd-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="400fd-105">&nbsp;&nbsp;[**\<system.service모델>**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="400fd-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="400fd-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<서비스호스팅환경>**](servicehostingenvironment.md)</span><span class="sxs-lookup"><span data-stu-id="400fd-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)</span></span>\
<span data-ttu-id="400fd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<베이스주소사전필터>**](baseaddressprefixfilters.md)</span><span class="sxs-lookup"><span data-stu-id="400fd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<baseAddressPrefixFilters>**](baseaddressprefixfilters.md)</span></span>\
<span data-ttu-id="400fd-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>추가**</span><span class="sxs-lookup"><span data-stu-id="400fd-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="400fd-109">구문</span><span class="sxs-lookup"><span data-stu-id="400fd-109">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <baseAddressPrefixFilters>
    <add prefix="String" />
  </baseAddressPrefixFilters>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="400fd-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="400fd-110">Attributes and Elements</span></span>  
 <span data-ttu-id="400fd-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="400fd-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="400fd-112">특성</span><span class="sxs-lookup"><span data-stu-id="400fd-112">Attributes</span></span>  
  
|<span data-ttu-id="400fd-113">attribute</span><span class="sxs-lookup"><span data-stu-id="400fd-113">Attribute</span></span>|<span data-ttu-id="400fd-114">Description</span><span class="sxs-lookup"><span data-stu-id="400fd-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="400fd-115">접두사</span><span class="sxs-lookup"><span data-stu-id="400fd-115">prefix</span></span>|<span data-ttu-id="400fd-116">기본 주소의 일부와 일치하는지 비교하는 데 사용되는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="400fd-116">A URI that is used to match a part of a base address.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="400fd-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="400fd-117">Child Elements</span></span>  
 <span data-ttu-id="400fd-118">없음</span><span class="sxs-lookup"><span data-stu-id="400fd-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="400fd-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="400fd-119">Parent Elements</span></span>  
  
|<span data-ttu-id="400fd-120">요소</span><span class="sxs-lookup"><span data-stu-id="400fd-120">Element</span></span>|<span data-ttu-id="400fd-121">Description</span><span class="sxs-lookup"><span data-stu-id="400fd-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="400fd-122">\<베이스주소사전필터></span><span class="sxs-lookup"><span data-stu-id="400fd-122">\<baseAddressPrefixFilters></span></span>](baseaddressprefixfilters.md)|<span data-ttu-id="400fd-123">IIS에서 WCF(Windows 통신 재단) 응용 프로그램을 호스팅할 때 적절한 IIS 바인딩을 선택하는 메커니즘을 제공하는 통과 필터를 지정하는 구성 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="400fd-123">A collection of configuration elements that specify pass-through filters, which provide a mechanism to pick the appropriate IIS bindings when hosting a Windows Communication Foundation (WCF) application in IIS.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="400fd-124">설명</span><span class="sxs-lookup"><span data-stu-id="400fd-124">Remarks</span></span>  
 <span data-ttu-id="400fd-125">접두사 필터는 공유 호스팅 공급자가 서비스에 사용될 URI를 지정하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="400fd-125">A prefix filter provides a way for shared hosting providers to specify which URIs are to be used by the service.</span></span> <span data-ttu-id="400fd-126">이 방법을 사용하면 공유 호스트가 동일한 사이트의 동일한 체계에 대해 기본 주소가 다른 여러 애플리케이션을 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="400fd-126">It enables shared hosts to host multiple applications with different base addresses for the same scheme on the same site.</span></span>  
  
 <span data-ttu-id="400fd-127">IIS 웹 사이트는 가상 디렉터리를 포함하는 가상 애플리케이션의 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="400fd-127">IIS Web sites are containers for virtual applications which contain virtual directories.</span></span> <span data-ttu-id="400fd-128">사이트의 애플리케이션은 하나 이상의 IIS 바인딩을 통해 액세스될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="400fd-128">The application in a site can be accessed through one or more IIS binding.</span></span> <span data-ttu-id="400fd-129">IIS 바인딩은 바인딩 프로토콜과 바인딩 정보라는 두 가지 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="400fd-129">IIS bindings provide two pieces of information: binding protocol and binding information.</span></span> <span data-ttu-id="400fd-130">바인딩 프로토콜(예: HTTP)은 통신이 이루어지는 체계를 정의하며, 바인딩 정보(예: IP 주소, 포트, Hostheader)는 사이트 액세스에 사용되는 데이터를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="400fd-130">Binding protocol (for example, HTTP) defines the scheme over which communication occurs, and binding information (for example, IP Address, Port, Hostheader) contains data used to access the site.</span></span>  
  
 <span data-ttu-id="400fd-131">IIS에서는 각 사이트에 대해 여러 개의 IIS 바인딩을 지정할 수 있으므로, 각 체계에 대해 여러 개의 기본 주소가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="400fd-131">IIS supports specifying multiple IIS bindings for each site, which results in multiple base addresses for each scheme.</span></span> <span data-ttu-id="400fd-132">사이트에서 호스팅되는 WCF 서비스는 각 스키마에 대해 하나의 기본 주소만 바인딩할 수 있으므로 접두사 필터 기능을 사용하여 호스팅된 서비스의 필수 기본 주소를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="400fd-132">Because a WCF service hosted under a site allows binding to only one base address for each scheme, you can use the prefix filter feature to pick the required base address of the hosted service.</span></span> <span data-ttu-id="400fd-133">IIS에서 제공하는 들어오는 기본 주소는 선택적 접두사 목록 필터를 기반으로 필터링됩니다.</span><span class="sxs-lookup"><span data-stu-id="400fd-133">The incoming base addresses, supplied by IIS, are filtered based on the optional prefix list filter.</span></span>  
  
 <span data-ttu-id="400fd-134">예를 들어 사이트에 다음과 같은 기본 주소가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="400fd-134">For example, your site can contain the following base addresses:</span></span>
  
```
http://testl.fabrikam.com/Service.svc  
http://test2.fabrikam.com/Service.svc  
```  
  
 <span data-ttu-id="400fd-135">다음 구성 파일을 사용하여 appdomain 수준에서 접두사 필터를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="400fd-135">You can use the following configuration file to specify a prefix filter at the appdomain level.</span></span>  
  
```xml  
<system.serviceModel>
  <serviceHostingEnvironment>
    <baseAddressPrefixFilters>
      <add prefix="net.tcp://test1.fabrikam.com:8000" />
      <add prefix="http://test2.fabrikam.com:9000" />
    </baseAddressPrefixFilters>
  </serviceHostingEnvironment>
</system.serviceModel>
```  
  
 <span data-ttu-id="400fd-136">이 예제에서 `net.tcp://test1.fabrikam.com:8000` 및 `http://test2.fabrikam.com:9000`은 해당 체계에서 통과되도록 허용된 유일한 기본 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="400fd-136">In this example, `net.tcp://test1.fabrikam.com:8000` and `http://test2.fabrikam.com:9000` are the only base addresses for their respective schemes which are allowed to be passed through.</span></span>  
  
 <span data-ttu-id="400fd-137">기본적으로, 접두사가 지정되지 않으면 모든 주소가 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="400fd-137">By default, when prefix is not specified, all addresses are passed through.</span></span> <span data-ttu-id="400fd-138">접두사를 지정하면 해당 체계에서 일치하는 기본 주소만 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="400fd-138">Specifying the prefix only allows the matching base address for that scheme to be passed through.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="400fd-139">필터는 와일드카드를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="400fd-139">The filter does not support any wildcards.</span></span> <span data-ttu-id="400fd-140">또한 IIS에서 제공하는 baseAddress는 `baseAddressPrefixFilters` 목록에 없는 다른 체계에 바인딩되는 주소를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="400fd-140">In addition, the baseAddresses supplied by IIS may have addresses bound to other schemes not present in the `baseAddressPrefixFilters` list.</span></span> <span data-ttu-id="400fd-141">이러한 주소는 필터링되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="400fd-141">These addresses are not filtered out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="400fd-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="400fd-142">See also</span></span>

- <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="400fd-143">호스팅</span><span class="sxs-lookup"><span data-stu-id="400fd-143">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
