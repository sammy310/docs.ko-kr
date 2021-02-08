---
description: 다음에 대해 자세히 알아보세요. <serviceHostingEnvironment>
title: <serviceHostingEnvironment>
ms.date: 03/30/2017
ms.assetid: 4f8a7c4f-e735-4987-979a-b74fcdae2652
ms.openlocfilehash: 95243a1cf9cea734b7f35a1400a8b5b865767976
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786722"
---
# \<serviceHostingEnvironment>

<span data-ttu-id="165f5-102">이 요소는 특정 전송을 위해 서비스 호스팅 환경에서 인스턴스화하는 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-102">This element defines the type the service hosting environment instantiates for a particular transport.</span></span> <span data-ttu-id="165f5-103">이 요소가 비어 있으면 기본 형식이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-103">If this element is empty, the default type is used.</span></span> <span data-ttu-id="165f5-104">이 요소는 애플리케이션이나 컴퓨터 수준 구성 파일에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-104">This element can only be used at the application or machine level configuration files.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceHostingEnvironment>**  
  
## <a name="syntax"></a><span data-ttu-id="165f5-105">구문</span><span class="sxs-lookup"><span data-stu-id="165f5-105">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment aspNetCompatibilityEnabled="Boolean"
                           minFreeMemoryPercentageToActivateService="Integer"
                           multipleSiteBindingsEnabled="Boolean">
  <baseAddressPrefixFilters>
    <add prefix="string" />
  </baseAddressPrefixFilters>
  <serviceActivations>
    <add factory="String"
         service="String" />
  </serviceActivations>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="165f5-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="165f5-106">Attributes and Elements</span></span>  

 <span data-ttu-id="165f5-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="165f5-108">특성</span><span class="sxs-lookup"><span data-stu-id="165f5-108">Attributes</span></span>  
  
|<span data-ttu-id="165f5-109">attribute</span><span class="sxs-lookup"><span data-stu-id="165f5-109">Attribute</span></span>|<span data-ttu-id="165f5-110">설명</span><span class="sxs-lookup"><span data-stu-id="165f5-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="165f5-111">aspNetCompatibilityEnabled</span><span class="sxs-lookup"><span data-stu-id="165f5-111">aspNetCompatibilityEnabled</span></span>|<span data-ttu-id="165f5-112">현재 애플리케이션에 ASP.NET 호환 모드를 설정했는지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-112">A Boolean value indicating whether the ASP.NET compatibility mode has been turned on for the current application.</span></span> <span data-ttu-id="165f5-113">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-113">The default is `false`.</span></span><br /><br /> <span data-ttu-id="165f5-114">이 특성이로 설정 되 면 `true` WCF (Windows Communication Foundation 요청) 서비스가 ASP.NET http 파이프라인을 통해 전달 되 고, http가 아닌 프로토콜을 통한 통신이 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-114">When this attribute is set to `true`, requests to Windows Communication Foundation (WCF) services flow through the ASP.NET HTTP pipeline, and communication over non-HTTP protocols is prohibited.</span></span> <span data-ttu-id="165f5-115">자세한 내용은 [WCF 서비스 및 ASP.NET](../../../wcf/feature-details/wcf-services-and-aspnet.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="165f5-115">For more information, see [WCF Services and ASP.NET](../../../wcf/feature-details/wcf-services-and-aspnet.md).</span></span>|  
|<span data-ttu-id="165f5-116">minFreeMemoryPercentageToActivateService</span><span class="sxs-lookup"><span data-stu-id="165f5-116">minFreeMemoryPercentageToActivateService</span></span>|<span data-ttu-id="165f5-117">WCF 서비스를 활성화할 수 있습니다 시스템에 사용할 수 있는 사용 가능한 메모리의 최소 크기를 지정 하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-117">An integer that specifies the minimum amount of free memory that should be available to the system, before a WCF service can be activated.</span></span> <span data-ttu-id="165f5-118">**주의:**  WCF 서비스의 web.config 파일에서 부분 신뢰와 함께이 특성을 지정 하면 <xref:System.Security.SecurityException> 서비스가 실행 될 때이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-118">**Caution:**  Specifying this attribute along with partial trust in the web.config file of a WCF service will result in a <xref:System.Security.SecurityException> when the service is run.</span></span>|  
|<span data-ttu-id="165f5-119">multipleSiteBindingsEnabled</span><span class="sxs-lookup"><span data-stu-id="165f5-119">multipleSiteBindingsEnabled</span></span>|<span data-ttu-id="165f5-120">사이트별로 여러 IIS 바인딩을 사용할 수 있는지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-120">A Boolean value that specifies whether multiple IIS bindings per site is enabled.</span></span><br /><br /> <span data-ttu-id="165f5-121">IIS는 가상 디렉터리를 포함하는 가상 애플리케이션의 컨테이너인 웹 사이트로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-121">IIS consists of web sites, which are containers for virtual applications containing virtual directories.</span></span> <span data-ttu-id="165f5-122">사이트의 애플리케이션은 하나 이상의 IIS 바인딩을 통해 액세스될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-122">The application in a site can be accessed through one or more IIS binding.</span></span> <span data-ttu-id="165f5-123">하나의 IIS 바인딩은 바인딩 프로토콜과 바인딩 정보라는 두 가지 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-123">An IIS binding provides two pieces of information: a binding protocol and binding information.</span></span> <span data-ttu-id="165f5-124">바인딩 프로토콜은 통신이 이루어지는 체계를 정의하며, 바인딩 정보는 사이트에 액세스하는 데 사용되는 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-124">Binding protocol defines the scheme over which communication occurs, and binding information is the information used to access the site.</span></span> <span data-ttu-id="165f5-125">바인딩 프로토콜의 예로는 HTTP가 있으며 바인딩 정보에는 IP 주소, 포트, 호스트 헤더 등이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-125">An example of a binding protocol can be HTTP, whereas binding information can contain an IP address, Port, host header, etc.</span></span><br /><br /> <span data-ttu-id="165f5-126">IIS에서는 사이트별로 여러 개의 IIS 바인딩을 지정할 수 있으므로, 체계별로 여러 개의 기본 주소가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-126">IIS supports specifying multiple IIS bindings per site, which results in multiple base addresses per scheme.</span></span> <span data-ttu-id="165f5-127">그러나 사이트에서 호스팅되는 Windows Communication Foundation (WCF) 서비스에는 체계 별로 하나의 baseAddress에 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-127">However, a Windows Communication Foundation (WCF) service hosted under a site allows binding to only one baseAddress per scheme.</span></span><br /><br /> <span data-ttu-id="165f5-128">Windows Communication Foundation (WCF) 서비스에 대해 사이트별로 여러 IIS 바인딩을 사용 하도록 설정 하려면이 특성을로 설정 `true` 합니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-128">To enable multiple IIS bindings per site for a Windows Communication Foundation (WCF) service, set this attribute to `true`.</span></span> <span data-ttu-id="165f5-129">여러 사이트 바인딩은 HTTP 프로토콜에 대해서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-129">Notice that multiple site binding is supported only for the HTTP protocol.</span></span> <span data-ttu-id="165f5-130">구성 파일의 엔드포인트 주소는 전체 URI여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-130">The address of endpoints in the configuration file needs to be a complete URI.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="165f5-131">자식 요소</span><span class="sxs-lookup"><span data-stu-id="165f5-131">Child Elements</span></span>  
  
|<span data-ttu-id="165f5-132">요소</span><span class="sxs-lookup"><span data-stu-id="165f5-132">Element</span></span>|<span data-ttu-id="165f5-133">설명</span><span class="sxs-lookup"><span data-stu-id="165f5-133">Description</span></span>|  
|-------------|-----------------|  
|[\<baseAddressPrefixFilters>](baseaddressprefixfilters.md)|<span data-ttu-id="165f5-134">서비스 호스트에서 사용하는 기본 주소에 대한 접두사 필터를 지정하는 구성 요소 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-134">A collection of configuration elements that specify prefix filters for the base addresses used by the service host.</span></span>|  
|[\<serviceActivations>](serviceactivations.md)|<span data-ttu-id="165f5-135">활성화 설정을 설명하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-135">A configuration section that describes activation settings.</span></span>|  
|[\<transportConfigurationTypes>](transportconfigurationtypes.md)|<span data-ttu-id="165f5-136">특정 전송의 형식을 식별하는 구성 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-136">A collection of configuration elements that identify the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="165f5-137">부모 요소</span><span class="sxs-lookup"><span data-stu-id="165f5-137">Parent Elements</span></span>  
  
|<span data-ttu-id="165f5-138">요소</span><span class="sxs-lookup"><span data-stu-id="165f5-138">Element</span></span>|<span data-ttu-id="165f5-139">설명</span><span class="sxs-lookup"><span data-stu-id="165f5-139">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="165f5-140">serviceModel</span><span class="sxs-lookup"><span data-stu-id="165f5-140">serviceModel</span></span>|<span data-ttu-id="165f5-141">모든 WCF(Windows Communication Foundation) 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-141">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="165f5-142">설명</span><span class="sxs-lookup"><span data-stu-id="165f5-142">Remarks</span></span>  

 <span data-ttu-id="165f5-143">기본적으로 WCF 서비스는 호스트된 애플리케이션 도메인(AppDomain)에서 ASP.NET과 함께 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-143">By default, WCF services run side-by-side with ASP.NET in hosted Application Domains (AppDomain).</span></span> <span data-ttu-id="165f5-144">동일한 AppDomain에서 WCF와 ASP.NET을 함께 사용할 수 있더라도 WCF 요청은 기본적으로 ASP.NET HTTP 파이프라인에 의해 처리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-144">Even though WCF and ASP.NET can coexist in the same AppDomain, WCF requests are not processed by the ASP.NET HTTP Pipeline by default.</span></span> <span data-ttu-id="165f5-145">따라서 ASP.NET 애플리케이션 플랫폼의 여러 요소를 WCF 서비스에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-145">As a result, several elements of the ASP.NET application platform are not available to WCF services.</span></span> <span data-ttu-id="165f5-146">여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-146">These include</span></span>  
  
- <span data-ttu-id="165f5-147">ASP.NET 파일/URL 권한 부여</span><span class="sxs-lookup"><span data-stu-id="165f5-147">ASP.NET File/URL Authorization</span></span>  
  
- <span data-ttu-id="165f5-148">ASP.NET 가장</span><span class="sxs-lookup"><span data-stu-id="165f5-148">ASP.NET Impersonation</span></span>  
  
- <span data-ttu-id="165f5-149">쿠키 기반 세션 상태</span><span class="sxs-lookup"><span data-stu-id="165f5-149">Cookie-based Session State</span></span>  
  
- <span data-ttu-id="165f5-150">HttpContext.Current</span><span class="sxs-lookup"><span data-stu-id="165f5-150">HttpContext.Current</span></span>  
  
- <span data-ttu-id="165f5-151">사용자 지정 HttpModule을 통한 파이프라인 확장성</span><span class="sxs-lookup"><span data-stu-id="165f5-151">Pipeline Extensibility via custom HttpModule</span></span>  
  
 <span data-ttu-id="165f5-152">WCF 서비스가 ASP.NET 컨텍스트에서 작동해야 하고 이 서비스가 HTTP를 통해서만 통신하는 경우 WCF의 ASP.NET 호환 모드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-152">If your WCF services need to function in the ASP.NET context, and communicate only over HTTP, you can use WCF’s ASP.NET compatibility mode.</span></span> <span data-ttu-id="165f5-153">이 모드는 애플리케이션 수준에서 `aspNetCompatibilityEnabled` 특성이 `true`로 설정되면 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-153">This mode is turned on when the `aspNetCompatibilityEnabled` attribute is set to `true` at the application level.</span></span> <span data-ttu-id="165f5-154">서비스 구현에서는 <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> 클래스를 사용하여 호환 모드에서 실행되는 기능을 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-154">Service implementations must declare their ability to run in compatibility mode using the <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> class.</span></span> <span data-ttu-id="165f5-155">호환 모드를 사용하는 경우 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-155">When the compatibility mode is enabled,</span></span>  
  
- <span data-ttu-id="165f5-156">ASP.NET 파일/URL 권한 부여가 WCF 인증 전에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-156">ASP.NET File/URL Authorization is enforced prior to WCF authorization.</span></span> <span data-ttu-id="165f5-157">권한 부여 결정은 요청의 전송 수준 ID에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-157">An authorization decision is based on the transport-level identity of the request.</span></span> <span data-ttu-id="165f5-158">메시지 수준의 ID가 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-158">Identities at the message level are ignored.</span></span>  
  
- <span data-ttu-id="165f5-159">WCF 서비스 작업이 ASP.NET 가장 컨텍스트에서 실행되기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-159">WCF service operations start to execute in the ASP.NET impersonation context.</span></span> <span data-ttu-id="165f5-160">ASP.NET 가장 및 WCF 가장이 모두 특정 서비스에 사용하도록 설정되면 WCF 가장 컨텍스트가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-160">If both ASP.NET impersonation and WCF impersonation are enabled for a specific service, the WCF impersonation context applies.</span></span>  
  
- <span data-ttu-id="165f5-161">HttpContext.Current는 WCF 서비스 코드에서 사용할 수 있으며, 서비스에서 HTTP가 아닌 엔드포인트를 노출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-161">HttpContext.Current can be used from WCF service code, and services are prevented from exposing non-HTTP endpoints.</span></span>  
  
- <span data-ttu-id="165f5-162">WCF 요청은 ASP.NET 파이프라인에서 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-162">WCF requests are processed by the ASP.NET pipeline.</span></span> <span data-ttu-id="165f5-163">들어오는 요청에서 동작하도록 구성된 HttpModule에서는 WCF 요청도 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-163">HttpModules that have been configured to act on incoming requests can also process WCF requests.</span></span> <span data-ttu-id="165f5-164">여기에는 사용자 지정 타사 모듈뿐만 아니라 <xref:System.Web.SessionState.SessionStateModule>과 같은 ASP.NET 플랫폼 구성 요소가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-164">These can include ASP.NET platform components (e.g., <xref:System.Web.SessionState.SessionStateModule>), as well as custom third party modules.</span></span>  
  
## <a name="example"></a><span data-ttu-id="165f5-165">예제</span><span class="sxs-lookup"><span data-stu-id="165f5-165">Example</span></span>  

 <span data-ttu-id="165f5-166">다음 코드 샘플에서는 ASP 호환 모드를 사용하도록 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="165f5-166">The following code sample shows how to enable ASP Compatibility Mode.</span></span>  
  
## <a name="code"></a><span data-ttu-id="165f5-167">코드</span><span class="sxs-lookup"><span data-stu-id="165f5-167">Code</span></span>  
  
```xml  
<serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>
```  
  
## <a name="see-also"></a><span data-ttu-id="165f5-168">참조</span><span class="sxs-lookup"><span data-stu-id="165f5-168">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="165f5-169">호스팅</span><span class="sxs-lookup"><span data-stu-id="165f5-169">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
- [<span data-ttu-id="165f5-170">WCF 서비스 및 ASP.NET</span><span class="sxs-lookup"><span data-stu-id="165f5-170">WCF Services and ASP.NET</span></span>](../../../wcf/feature-details/wcf-services-and-aspnet.md)
