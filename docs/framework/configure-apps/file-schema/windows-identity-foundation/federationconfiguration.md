---
title: <federationConfiguration>
ms.date: 03/30/2017
ms.assetid: 8b14054c-6d07-46ab-ab58-03f14beac0f2
author: BrucePerlerMS
ms.openlocfilehash: bcd8e00b770517e3faff011b4acee08ebdc5a0df
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152738"
---
# <a name="federationconfiguration"></a><span data-ttu-id="87c65-101">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="87c65-101">\<federationConfiguration></span></span>
<span data-ttu-id="87c65-102">WS-페더레이션 프로토콜을 통해 페더레이션 인증을 사용하는 경우 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) 및 <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM)을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="87c65-102">Configures the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) when using federated authentication through the WS-Federation protocol.</span></span> <span data-ttu-id="87c65-103">클레임 기반 <xref:System.Security.Claims.ClaimsAuthorizationManager> 액세스 제어를 <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> 제공 하도록 또는 클래스를 사용 하는 경우를 구성 합니다. <xref:System.IdentityModel.Services.ClaimsPrincipalPermission></span><span class="sxs-lookup"><span data-stu-id="87c65-103">Configures the <xref:System.Security.Claims.ClaimsAuthorizationManager> when using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control.</span></span>  
  
<span data-ttu-id="87c65-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="87c65-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="87c65-105">&nbsp;&nbsp;[**\<system.identityModel.서비스>**](system-identitymodel-services.md)</span><span class="sxs-lookup"><span data-stu-id="87c65-105">&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)</span></span>\
<span data-ttu-id="87c65-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<페더레이션구성>**</span><span class="sxs-lookup"><span data-stu-id="87c65-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<federationConfiguration>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87c65-107">구문</span><span class="sxs-lookup"><span data-stu-id="87c65-107">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="87c65-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="87c65-108">Attributes and Elements</span></span>  
 <span data-ttu-id="87c65-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="87c65-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="87c65-110">특성</span><span class="sxs-lookup"><span data-stu-id="87c65-110">Attributes</span></span>  
  
|<span data-ttu-id="87c65-111">attribute</span><span class="sxs-lookup"><span data-stu-id="87c65-111">Attribute</span></span>|<span data-ttu-id="87c65-112">Description</span><span class="sxs-lookup"><span data-stu-id="87c65-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="87c65-113">name</span><span class="sxs-lookup"><span data-stu-id="87c65-113">name</span></span>|<span data-ttu-id="87c65-114">이 페더레이션 구성 요소의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="87c65-114">The name of this federation configuration element.</span></span> <span data-ttu-id="87c65-115">이 특성은 주로 향후 프로토콜에 대한 확장성 지점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="87c65-115">This attribute primarily provides an extensibility point for future protocols.</span></span> <span data-ttu-id="87c65-116">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="87c65-116">Optional.</span></span>|  
|<span data-ttu-id="87c65-117">ID구성 이름</span><span class="sxs-lookup"><span data-stu-id="87c65-117">identityConfigurationName</span></span>|<span data-ttu-id="87c65-118">[ \<idConfiguration에](identityconfiguration.md) 지정된 ID 구성 섹션의 이름은 사용할 구성 요소구성>.</span><span class="sxs-lookup"><span data-stu-id="87c65-118">The name of the identity configuration section as specified in an [\<identityConfiguration>](identityconfiguration.md) element to use.</span></span> <span data-ttu-id="87c65-119">이 특성을 지정하지 않으면 기본 ID 구성 섹션이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="87c65-119">If this attribute is not specified, the default identity configuration section is used.</span></span> <span data-ttu-id="87c65-120">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="87c65-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="87c65-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="87c65-121">Child Elements</span></span>  
  
|<span data-ttu-id="87c65-122">요소</span><span class="sxs-lookup"><span data-stu-id="87c65-122">Element</span></span>|<span data-ttu-id="87c65-123">Description</span><span class="sxs-lookup"><span data-stu-id="87c65-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="87c65-124">\<쿠키핸들러></span><span class="sxs-lookup"><span data-stu-id="87c65-124">\<cookieHandler></span></span>](cookiehandler.md)|<span data-ttu-id="87c65-125">SAM에서 사용하는 쿠키 처리기를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="87c65-125">Configures the cookie handler used by the SAM.</span></span> <span data-ttu-id="87c65-126">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="87c65-126">Optional.</span></span>|  
|[<span data-ttu-id="87c65-127">\<서비스인증서></span><span class="sxs-lookup"><span data-stu-id="87c65-127">\<serviceCertificate></span></span>](servicecertificate.md)|<span data-ttu-id="87c65-128">토큰을 암호화하고 해독하는 데 사용되는 인증서를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="87c65-128">Configures the certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="87c65-129">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="87c65-129">Optional.</span></span>|  
|[<span data-ttu-id="87c65-130">\<ws페더레이션></span><span class="sxs-lookup"><span data-stu-id="87c65-130">\<wsFederation></span></span>](wsfederation.md)|<span data-ttu-id="87c65-131">WS-페더레이션 인증 모듈(WSFAM)을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="87c65-131">Configures the WS-Federation Authentication Module (WSFAM).</span></span> <span data-ttu-id="87c65-132">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="87c65-132">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="87c65-133">부모 요소</span><span class="sxs-lookup"><span data-stu-id="87c65-133">Parent Elements</span></span>  
  
|<span data-ttu-id="87c65-134">요소</span><span class="sxs-lookup"><span data-stu-id="87c65-134">Element</span></span>|<span data-ttu-id="87c65-135">Description</span><span class="sxs-lookup"><span data-stu-id="87c65-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="87c65-136">\<system.identityModel.서비스></span><span class="sxs-lookup"><span data-stu-id="87c65-136">\<system.identityModel.services></span></span>](system-identitymodel-services.md)|<span data-ttu-id="87c65-137">WS-페더레이션 프로토콜을 사용하여 인증하기 위한 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="87c65-137">Configuration section for authentication using the WS-Federation protocol.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87c65-138">설명</span><span class="sxs-lookup"><span data-stu-id="87c65-138">Remarks</span></span>  
 <span data-ttu-id="87c65-139">\<페더레이션구성> 요소는 다음과 같은 두 가지 시나리오에서 설정을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="87c65-139">The \<federationConfiguration> element provides settings in two different scenarios:</span></span>  
  
- <span data-ttu-id="87c65-140">수동 웹 응용 프로그램에서 WS-페더레이션을 사용하는 경우 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> 요소에는 (SFAM) 및 (SAM)을 구성하는 설정이 <xref:System.IdentityModel.Services.SessionAuthenticationModule> 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87c65-140">When using WS-Federation in a passive Web application, the element contains settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span> <span data-ttu-id="87c65-141">또한 보안 토큰 처리기 및 인증서및 클레임 권한 부여 관리자 및 클레임 인증 관리자와 같은 구성 요소를 구성하는 데 사용할 ID 구성을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="87c65-141">It also references the identity configuration to be used to configure security token handlers and certificates, and components like the claims authorization manager and the claims authentication manager.</span></span>  
  
- <span data-ttu-id="87c65-142"><xref:System.IdentityModel.Services.ClaimsPrincipalPermission> 또는 클래스를 <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> 사용하여 코드에서 클레임 기반 액세스 제어를 제공하는 경우 요소는 권한 부여 결정을 내리는 데 사용되는 클레임 권한 부여 관리자 및 정책을 구성하는 ID 구성을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="87c65-142">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the element references the identity configuration that configures the claims authorization manager and policy that is used to make authorization decisions.</span></span> <span data-ttu-id="87c65-143">수동 웹 시나리오가 아닌 시나리오에서도 마찬가지입니다. 예를 들어 WCF(Windows 통신 재단) 응용 프로그램 또는 웹 기반이 아닌 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="87c65-143">This is true, even in scenarios that are not passive Web scenarios; for example, Windows Communication Foundation (WCF) applications or an application that is not Web-based.</span></span> <span data-ttu-id="87c65-144">응용 프로그램이 수동 웹 응용 프로그램이 아닌 경우 element에서 `<federationConfiguration>` [ \<](claimsauthorizationmanager.md) 참조하는 ID 구성의 클레임AuthorizationManager>요소(및 해당 자식 정책 요소)가 적용되는 유일한 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="87c65-144">If the application is not a passive Web application, the [\<claimsAuthorizationManager>](claimsauthorizationmanager.md) element (and its child policy elements, if present) of the identity configuration referenced by the `<federationConfiguration>` element are the only settings applied.</span></span> <span data-ttu-id="87c65-145">다른 특성은 모두 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="87c65-145">All others are ignored.</span></span>  
  
 <span data-ttu-id="87c65-146">시나리오에 관계없이 런타임은 기본 페더레이션 구성을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="87c65-146">Regardless of the scenario, the runtime loads the default federation configuration.</span></span> <span data-ttu-id="87c65-147">동작은 다음과 같이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="87c65-147">The behavior is defined as follows:</span></span>  
  
1. <span data-ttu-id="87c65-148">요소가 없는 `<federationConfiguration>` 경우 런타임은 페더레이션 구성을 만들고 기본값으로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="87c65-148">If there is no `<federationConfiguration>` element present, the runtime creates a federation configuration and populates it with default values.</span></span> <span data-ttu-id="87c65-149">이 기본 페더레이션 구성은 기본 ID 구성을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="87c65-149">This default federation configuration will reference the default identity configuration.</span></span>  
  
2. <span data-ttu-id="87c65-150">단일 `<federationConfiguration>` 요소가 있는 경우 명명 또는 이름 없는 여부에 관계없이 기본 페더레이션 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="87c65-150">If a single `<federationConfiguration>` element is present, it is the default federation configuration regardless of whether it is named or unnamed.</span></span> <span data-ttu-id="87c65-151">해당 `identityConfiguration` 특성을 지정하면 명명된 ID 구성이 참조됩니다. 그렇지 않으면 기본 ID 구성이 참조됩니다.</span><span class="sxs-lookup"><span data-stu-id="87c65-151">If its `identityConfiguration` attribute is specified, the named identity configuration is referenced; otherwise, the default identity configuration is referenced.</span></span>  
  
3. <span data-ttu-id="87c65-152">명명되지 `<federationConfiguration>` 않은 요소가 있으면 기본 페더레이션 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="87c65-152">If an unnamed `<federationConfiguration>` element is present, it is the default federation configuration.</span></span> <span data-ttu-id="87c65-153">해당 `identityConfiguration` 특성을 지정하면 명명된 ID 구성이 참조됩니다. 그렇지 않으면 기본 ID 구성이 참조됩니다.</span><span class="sxs-lookup"><span data-stu-id="87c65-153">If its `identityConfiguration` attribute is specified, the named identity configuration is referenced; otherwise, the default identity configuration is referenced.</span></span>  
  
4. <span data-ttu-id="87c65-154">명명된 `<federationConfiguration>` 요소가 여러 개 있고 `<federationConfiguration>` 명명되지 않은 요소가 없는 경우 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="87c65-154">If multiple named `<federationConfiguration>` elements are present and no unnamed `<federationConfiguration>` element is present, an exception is thrown.</span></span>  
  
 <span data-ttu-id="87c65-155">일반적으로 단일 `<federationConfiguration>` 섹션만 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="87c65-155">Typically, only a single `<federationConfiguration>` section is defined.</span></span> <span data-ttu-id="87c65-156">이 섹션은 기본 페더레이션 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="87c65-156">This section is the default federation configuration.</span></span> <span data-ttu-id="87c65-157">고유한 이름의 `<federationConfiguration>` 여러 요소를 지정할 수 있습니다. 그러나 이 경우 명명되지 않은 구성이 아닌 페더레이션 구성을 로드하려면 에 대한 처리기를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87c65-157">You may specify multiple, uniquely-named `<federationConfiguration>` elements; however, in this case, if you want to load a federation configuration other than the unnamed one, you must provide a handler for the.</span></span> <span data-ttu-id="87c65-158"><xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated>처리기 내부의 <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> 속성을 구성 <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> 파일의 적절한 `<federationConfiguration>` 요소의 값으로 초기화된 개체로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="87c65-158"><xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated> event and set the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> property inside the handler to a <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> object initialized with values from the appropriate `<federationConfiguration>` element in the configuration file.</span></span>  
  
 <span data-ttu-id="87c65-159">합니다 `<federationConfiguration>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="87c65-159">The `<federationConfiguration>` element is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> class.</span></span> <span data-ttu-id="87c65-160">구성 개체 자체는 <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> 클래스로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="87c65-160">The configuration object itself is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> class.</span></span> <span data-ttu-id="87c65-161">단일 <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> 인스턴스는 <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> 속성에 설정되며 응용 프로그램에 대한 페더레이션 구성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="87c65-161">A single <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> instance is set on the <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> property and provides federated configuration for the application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="87c65-162">예제</span><span class="sxs-lookup"><span data-stu-id="87c65-162">Example</span></span>  
 <span data-ttu-id="87c65-163">다음 XML은 `<federationConfiguration>` WSFAM에 대한 설정을 지정하고 SAM에서 기본 쿠키 <xref:System.IdentityModel.Services.ChunkedCookieHandler> 처리기(클래스의 인스턴스)를 사용할 수 있도록 지정하는 요소를 보여 주며.</span><span class="sxs-lookup"><span data-stu-id="87c65-163">The following XML shows a `<federationConfiguration>` element that specifies settings for the WSFAM and specifies that the default cookie handler (an instance of the <xref:System.IdentityModel.Services.ChunkedCookieHandler> class) be used by the SAM.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="87c65-164">이 예제에서는 HTTPS를 사용할 때 쿠키 처리기나 WSFAM이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87c65-164">In this example, neither the cookie handler nor WSFAM are required to use HTTPS.</span></span> <span data-ttu-id="87c65-165">`requireHttps` 이는 `<wsFederation>` 요소의 특성과 의 `requireSsl` `<cookieHandlerElement>` 특성이 다음과 `false`기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="87c65-165">This is because the `requireHttps` attribute on the `<wsFederation>` element and the `requireSsl` attribute on the `<cookieHandlerElement>` are `false`.</span></span> <span data-ttu-id="87c65-166">이러한 설정은 보안 위험이 있을 수 있기 때문에 대부분의 프로덕션 환경에서는 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87c65-166">These settings are not recommended for most production environments as they may present a security risk.</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <wsFederation passiveRedirectEnabled="true"
      issuer="http://localhost:15839/wsFederationSTS/Issue"
      realm="http://localhost:50969/" reply="http://localhost:50969/"
      requireHttps="false"
      signOutReply="http://localhost:50969/SignedOutPage.html"
      signOutQueryString="Param1=value2&Param2=value2"
      persistentCookiesOnPassiveRedirects="true" />  
    <cookieHandler requireSsl="false" />  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="see-also"></a><span data-ttu-id="87c65-167">참고 항목</span><span class="sxs-lookup"><span data-stu-id="87c65-167">See also</span></span>

- <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>
- <xref:System.IdentityModel.Services.SessionAuthenticationModule>
- <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>
- [<span data-ttu-id="87c65-168">\<ID구성></span><span class="sxs-lookup"><span data-stu-id="87c65-168">\<identityConfiguration></span></span>](identityconfiguration.md)
