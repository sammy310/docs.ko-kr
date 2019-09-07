---
title: <serviceHostingEnvironment>
ms.date: 03/30/2017
ms.assetid: 4f8a7c4f-e735-4987-979a-b74fcdae2652
ms.openlocfilehash: 165dbed1b78d00f8d4dd3e482b9fee8a23db60da
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399621"
---
# <a name="servicehostingenvironment"></a><span data-ttu-id="19f54-101">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="19f54-101">\<serviceHostingEnvironment></span></span>
<span data-ttu-id="19f54-102">이 요소는 특정 전송을 위해 서비스 호스팅 환경에서 인스턴스화하는 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-102">This element defines the type the service hosting environment instantiates for a particular transport.</span></span> <span data-ttu-id="19f54-103">이 요소가 비어 있으면 기본 형식이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-103">If this element is empty, the default type is used.</span></span> <span data-ttu-id="19f54-104">이 요소는 응용 프로그램이나 컴퓨터 수준 구성 파일에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-104">This element can only be used at the application or machine level configuration files.</span></span>  
  
<span data-ttu-id="19f54-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="19f54-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="19f54-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="19f54-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="19f54-107">&nbsp;&nbsp;&nbsp;&nbsp; **\<serviceHostingEnvironment >**</span><span class="sxs-lookup"><span data-stu-id="19f54-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceHostingEnvironment>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19f54-108">구문</span><span class="sxs-lookup"><span data-stu-id="19f54-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="19f54-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="19f54-109">Attributes and Elements</span></span>  
 <span data-ttu-id="19f54-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="19f54-111">특성</span><span class="sxs-lookup"><span data-stu-id="19f54-111">Attributes</span></span>  
  
|<span data-ttu-id="19f54-112">특성</span><span class="sxs-lookup"><span data-stu-id="19f54-112">Attribute</span></span>|<span data-ttu-id="19f54-113">설명</span><span class="sxs-lookup"><span data-stu-id="19f54-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="19f54-114">aspNetCompatibilityEnabled</span><span class="sxs-lookup"><span data-stu-id="19f54-114">aspNetCompatibilityEnabled</span></span>|<span data-ttu-id="19f54-115">현재 응용 프로그램에 ASP.NET 호환 모드를 설정했는지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-115">A Boolean value indicating whether the ASP.NET compatibility mode has been turned on for the current application.</span></span> <span data-ttu-id="19f54-116">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-116">The default is `false`.</span></span><br /><br /> <span data-ttu-id="19f54-117">이 특성이로 `true`설정 되 면 WCF (Windows Communication Foundation 요청) 서비스가 ASP.NET http 파이프라인을 통해 전달 되 고, http가 아닌 프로토콜을 통한 통신이 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-117">When this attribute is set to `true`, requests to Windows Communication Foundation (WCF) services flow through the ASP.NET HTTP pipeline, and communication over non-HTTP protocols is prohibited.</span></span> <span data-ttu-id="19f54-118">자세한 내용은 [WCF 서비스 및 ASP.NET](../../../wcf/feature-details/wcf-services-and-aspnet.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="19f54-118">For more information, see [WCF Services and ASP.NET](../../../wcf/feature-details/wcf-services-and-aspnet.md).</span></span>|  
|<span data-ttu-id="19f54-119">minFreeMemoryPercentageToActivateService</span><span class="sxs-lookup"><span data-stu-id="19f54-119">minFreeMemoryPercentageToActivateService</span></span>|<span data-ttu-id="19f54-120">WCF 서비스를 활성화할 수 있습니다 시스템에 사용할 수 있는 사용 가능한 메모리의 최소 크기를 지정 하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-120">An integer that specifies the minimum amount of free memory that should be available to the system, before a WCF service can be activated.</span></span> <span data-ttu-id="19f54-121">**주의:**  WCF 서비스의 web.config 파일에서 부분 신뢰와 함께이 특성을 지정 하면 서비스가 실행 <xref:System.Security.SecurityException> 될 때이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-121">**Caution:**  Specifying this attribute along with partial trust in the web.config file of a WCF service will result in a <xref:System.Security.SecurityException> when the service is run.</span></span>|  
|<span data-ttu-id="19f54-122">multipleSiteBindingsEnabled</span><span class="sxs-lookup"><span data-stu-id="19f54-122">multipleSiteBindingsEnabled</span></span>|<span data-ttu-id="19f54-123">사이트별로 여러 IIS 바인딩을 사용할 수 있는지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-123">A Boolean value that specifies whether multiple IIS bindings per site is enabled.</span></span><br /><br /> <span data-ttu-id="19f54-124">IIS는 가상 디렉터리를 포함하는 가상 애플리케이션의 컨테이너인 웹 사이트로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-124">IIS consists of web sites, which are containers for virtual applications containing virtual directories.</span></span> <span data-ttu-id="19f54-125">사이트의 애플리케이션은 하나 이상의 IIS 바인딩을 통해 액세스될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-125">The application in a site can be accessed through one or more IIS binding.</span></span> <span data-ttu-id="19f54-126">하나의 IIS 바인딩은 바인딩 프로토콜과 바인딩 정보라는 두 가지 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-126">An IIS binding provides two pieces of information: a binding protocol and binding information.</span></span> <span data-ttu-id="19f54-127">바인딩 프로토콜은 통신이 이루어지는 체계를 정의하며, 바인딩 정보는 사이트에 액세스하는 데 사용되는 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-127">Binding protocol defines the scheme over which communication occurs, and binding information is the information used to access the site.</span></span> <span data-ttu-id="19f54-128">바인딩 프로토콜의 예로는 HTTP가 있으며 바인딩 정보에는 IP 주소, 포트, 호스트 헤더 등이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-128">An example of a binding protocol can be HTTP, whereas binding information can contain an IP address, Port, host header, etc.</span></span><br /><br /> <span data-ttu-id="19f54-129">IIS에서는 사이트별로 여러 개의 IIS 바인딩을 지정할 수 있으므로, 체계별로 여러 개의 기본 주소가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-129">IIS supports specifying multiple IIS bindings per site, which results in multiple base addresses per scheme.</span></span> <span data-ttu-id="19f54-130">그러나 사이트에서 호스팅되는 Windows Communication Foundation (WCF) 서비스에는 체계 별로 하나의 baseAddress에 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-130">However, a Windows Communication Foundation (WCF) service hosted under a site allows binding to only one baseAddress per scheme.</span></span><br /><br /> <span data-ttu-id="19f54-131">Windows Communication Foundation (WCF) 서비스에 대해 사이트별로 여러 IIS 바인딩을 사용 하도록 설정 하려면이 특성을 `true`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-131">To enable multiple IIS bindings per site for a Windows Communication Foundation (WCF) service, set this attribute to `true`.</span></span> <span data-ttu-id="19f54-132">여러 사이트 바인딩은 HTTP 프로토콜에 대해서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-132">Notice that multiple site binding is supported only for the HTTP protocol.</span></span> <span data-ttu-id="19f54-133">구성 파일의 끝점 주소는 전체 URI여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-133">The address of endpoints in the configuration file needs to be a complete URI.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="19f54-134">자식 요소</span><span class="sxs-lookup"><span data-stu-id="19f54-134">Child Elements</span></span>  
  
|<span data-ttu-id="19f54-135">요소</span><span class="sxs-lookup"><span data-stu-id="19f54-135">Element</span></span>|<span data-ttu-id="19f54-136">설명</span><span class="sxs-lookup"><span data-stu-id="19f54-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="19f54-137">\<baseAddressPrefixFilters></span><span class="sxs-lookup"><span data-stu-id="19f54-137">\<baseAddressPrefixFilters></span></span>](baseaddressprefixfilters.md)|<span data-ttu-id="19f54-138">서비스 호스트에서 사용하는 기본 주소에 대한 접두사 필터를 지정하는 구성 요소 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-138">A collection of configuration elements that specify prefix filters for the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="19f54-139">\<serviceActivations></span><span class="sxs-lookup"><span data-stu-id="19f54-139">\<serviceActivations></span></span>](serviceactivations.md)|<span data-ttu-id="19f54-140">활성화 설정을 설명하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-140">A configuration section that describes activation settings.</span></span>|  
|[<span data-ttu-id="19f54-141">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="19f54-141">\<transportConfigurationTypes></span></span>](transportconfigurationtypes.md)|<span data-ttu-id="19f54-142">특정 전송의 형식을 식별하는 구성 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-142">A collection of configuration elements that identify the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="19f54-143">부모 요소</span><span class="sxs-lookup"><span data-stu-id="19f54-143">Parent Elements</span></span>  
  
|<span data-ttu-id="19f54-144">요소</span><span class="sxs-lookup"><span data-stu-id="19f54-144">Element</span></span>|<span data-ttu-id="19f54-145">설명</span><span class="sxs-lookup"><span data-stu-id="19f54-145">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="19f54-146">serviceModel</span><span class="sxs-lookup"><span data-stu-id="19f54-146">serviceModel</span></span>|<span data-ttu-id="19f54-147">모든 WCF(Windows Communication Foundation) 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-147">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19f54-148">설명</span><span class="sxs-lookup"><span data-stu-id="19f54-148">Remarks</span></span>  
 <span data-ttu-id="19f54-149">기본적으로 WCF 서비스는 호스트된 응용프로그램 도메인(AppDomain)에서 ASP.NET과 함께 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-149">By default, WCF services run side-by-side with ASP.NET in hosted Application Domains (AppDomain).</span></span> <span data-ttu-id="19f54-150">동일한 AppDomain에서 WCF와 ASP.NET을 함께 사용할 수 있더라도 WCF 요청은 기본적으로 ASP.NET HTTP 파이프라인에 의해 처리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-150">Even though WCF and ASP.NET can coexist in the same AppDomain, WCF requests are not processed by the ASP.NET HTTP Pipeline by default.</span></span> <span data-ttu-id="19f54-151">따라서 ASP.NET 응용 프로그램 플랫폼의 여러 요소를 WCF 서비스에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-151">As a result, several elements of the ASP.NET application platform are not available to WCF services.</span></span> <span data-ttu-id="19f54-152">이러한 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-152">These include</span></span>  
  
- <span data-ttu-id="19f54-153">ASP.NET 파일/URL 권한 부여</span><span class="sxs-lookup"><span data-stu-id="19f54-153">ASP.NET File/URL Authorization</span></span>  
  
- <span data-ttu-id="19f54-154">ASP.NET 가장</span><span class="sxs-lookup"><span data-stu-id="19f54-154">ASP.NET Impersonation</span></span>  
  
- <span data-ttu-id="19f54-155">쿠키 기반 세션 상태</span><span class="sxs-lookup"><span data-stu-id="19f54-155">Cookie-based Session State</span></span>  
  
- <span data-ttu-id="19f54-156">HttpContext.Current</span><span class="sxs-lookup"><span data-stu-id="19f54-156">HttpContext.Current</span></span>  
  
- <span data-ttu-id="19f54-157">사용자 지정 HttpModule을 통한 파이프라인 확장성</span><span class="sxs-lookup"><span data-stu-id="19f54-157">Pipeline Extensibility via custom HttpModule</span></span>  
  
 <span data-ttu-id="19f54-158">WCF 서비스가 ASP.NET 컨텍스트에서 작동해야 하고 이 서비스가 HTTP를 통해서만 통신하는 경우 WCF의 ASP.NET 호환 모드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-158">If your WCF services need to function in the ASP.NET context, and communicate only over HTTP, you can use WCF’s ASP.NET compatibility mode.</span></span> <span data-ttu-id="19f54-159">이 모드는 응용 프로그램 수준에서 `aspNetCompatibilityEnabled` 특성이 `true`로 설정되면 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-159">This mode is turned on when the `aspNetCompatibilityEnabled` attribute is set to `true` at the application level.</span></span> <span data-ttu-id="19f54-160">서비스 구현에서는 <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> 클래스를 사용하여 호환 모드에서 실행되는 기능을 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-160">Service implementations must declare their ability to run in compatibility mode using the <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> class.</span></span> <span data-ttu-id="19f54-161">호환 모드를 사용하는 경우 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-161">When the compatibility mode is enabled,</span></span>  
  
- <span data-ttu-id="19f54-162">ASP.NET 파일/URL 권한 부여가 WCF 인증 전에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-162">ASP.NET File/URL Authorization is enforced prior to WCF authorization.</span></span> <span data-ttu-id="19f54-163">권한 부여 결정은 요청의 전송 수준 ID에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-163">An authorization decision is based on the transport-level identity of the request.</span></span> <span data-ttu-id="19f54-164">메시지 수준의 ID가 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-164">Identities at the message level are ignored.</span></span>  
  
- <span data-ttu-id="19f54-165">WCF 서비스 작업이 ASP.NET 가장 컨텍스트에서 실행되기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-165">WCF service operations start to execute in the ASP.NET impersonation context.</span></span> <span data-ttu-id="19f54-166">ASP.NET 가장 및 WCF 가장이 모두 특정 서비스에 사용하도록 설정되면 WCF 가장 컨텍스트가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-166">If both ASP.NET impersonation and WCF impersonation are enabled for a specific service, the WCF impersonation context applies.</span></span>  
  
- <span data-ttu-id="19f54-167">HttpContext.Current는 WCF 서비스 코드에서 사용할 수 있으며, 서비스에서 HTTP가 아닌 끝점을 노출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-167">HttpContext.Current can be used from WCF service code, and services are prevented from exposing non-HTTP endpoints.</span></span>  
  
- <span data-ttu-id="19f54-168">WCF 요청은 ASP.NET 파이프라인에서 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-168">WCF requests are processed by the ASP.NET pipeline.</span></span> <span data-ttu-id="19f54-169">들어오는 요청에서 동작하도록 구성된 HttpModule에서는 WCF 요청도 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-169">HttpModules that have been configured to act on incoming requests can also process WCF requests.</span></span> <span data-ttu-id="19f54-170">여기에는 사용자 지정 타사 모듈뿐만 아니라 <xref:System.Web.SessionState.SessionStateModule>과 같은 ASP.NET 플랫폼 구성 요소가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-170">These can include ASP.NET platform components (e.g., <xref:System.Web.SessionState.SessionStateModule>), as well as custom third party modules.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19f54-171">예제</span><span class="sxs-lookup"><span data-stu-id="19f54-171">Example</span></span>  
 <span data-ttu-id="19f54-172">다음 코드 샘플에서는 ASP 호환 모드를 사용하도록 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="19f54-172">The following code sample shows how to enable ASP Compatibility Mode.</span></span>  
  
## <a name="code"></a><span data-ttu-id="19f54-173">코드</span><span class="sxs-lookup"><span data-stu-id="19f54-173">Code</span></span>  
  
```xml  
<serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>
```  
  
## <a name="see-also"></a><span data-ttu-id="19f54-174">참고자료</span><span class="sxs-lookup"><span data-stu-id="19f54-174">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="19f54-175">호스팅</span><span class="sxs-lookup"><span data-stu-id="19f54-175">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
- [<span data-ttu-id="19f54-176">WCF 서비스 및 ASP.NET</span><span class="sxs-lookup"><span data-stu-id="19f54-176">WCF Services and ASP.NET</span></span>](../../../wcf/feature-details/wcf-services-and-aspnet.md)
