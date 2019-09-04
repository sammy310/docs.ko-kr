---
title: <federationConfiguration>
ms.date: 03/30/2017
ms.assetid: 8b14054c-6d07-46ab-ab58-03f14beac0f2
author: BrucePerlerMS
ms.openlocfilehash: 148b2f3e12fbfbf85b800f0ca7f5dc7dc1845d24
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252009"
---
# <a name="federationconfiguration"></a><span data-ttu-id="c6b15-101">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="c6b15-101">\<federationConfiguration></span></span>
<span data-ttu-id="c6b15-102">Ws-federation 프로토콜 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> 을 통해 페더레이션된 인증을 사용 하 <xref:System.IdentityModel.Services.SessionAuthenticationModule> 는 경우 (wsfam) 및 (SAM)을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b15-102">Configures the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) when using federated authentication through the WS-Federation protocol.</span></span> <span data-ttu-id="c6b15-103"><xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.Security.Claims.ClaimsAuthorizationManager> 또는<xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> 클래스를 사용 하 여 클레임 기반 액세스 제어를 제공 하는 경우를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b15-103">Configures the <xref:System.Security.Claims.ClaimsAuthorizationManager> when using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control.</span></span>  
  
<span data-ttu-id="c6b15-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c6b15-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c6b15-105">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel-services.md)</span><span class="sxs-lookup"><span data-stu-id="c6b15-105">&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)</span></span>\
<span data-ttu-id="c6b15-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<federationConfiguration >**</span><span class="sxs-lookup"><span data-stu-id="c6b15-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<federationConfiguration>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6b15-107">구문</span><span class="sxs-lookup"><span data-stu-id="c6b15-107">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c6b15-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c6b15-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c6b15-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b15-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c6b15-110">특성</span><span class="sxs-lookup"><span data-stu-id="c6b15-110">Attributes</span></span>  
  
|<span data-ttu-id="c6b15-111">특성</span><span class="sxs-lookup"><span data-stu-id="c6b15-111">Attribute</span></span>|<span data-ttu-id="c6b15-112">Description</span><span class="sxs-lookup"><span data-stu-id="c6b15-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c6b15-113">name</span><span class="sxs-lookup"><span data-stu-id="c6b15-113">name</span></span>|<span data-ttu-id="c6b15-114">이 페더레이션 구성 요소의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c6b15-114">The name of this federation configuration element.</span></span> <span data-ttu-id="c6b15-115">이 특성은 주로 이후 프로토콜에 대 한 확장성 지점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b15-115">This attribute primarily provides an extensibility point for future protocols.</span></span> <span data-ttu-id="c6b15-116">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c6b15-116">Optional.</span></span>|  
|<span data-ttu-id="c6b15-117">identityConfigurationName</span><span class="sxs-lookup"><span data-stu-id="c6b15-117">identityConfigurationName</span></span>|<span data-ttu-id="c6b15-118">사용할 [ \<identityConfiguration >](identityconfiguration.md) 요소에 지정 된 id 구성 섹션의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c6b15-118">The name of the identity configuration section as specified in an [\<identityConfiguration>](identityconfiguration.md) element to use.</span></span> <span data-ttu-id="c6b15-119">이 특성을 지정 하지 않으면 기본 id 구성 섹션이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6b15-119">If this attribute is not specified, the default identity configuration section is used.</span></span> <span data-ttu-id="c6b15-120">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c6b15-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c6b15-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c6b15-121">Child Elements</span></span>  
  
|<span data-ttu-id="c6b15-122">요소</span><span class="sxs-lookup"><span data-stu-id="c6b15-122">Element</span></span>|<span data-ttu-id="c6b15-123">설명</span><span class="sxs-lookup"><span data-stu-id="c6b15-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c6b15-124">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="c6b15-124">\<cookieHandler></span></span>](cookiehandler.md)|<span data-ttu-id="c6b15-125">SAM에서 사용 하는 쿠키 처리기를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b15-125">Configures the cookie handler used by the SAM.</span></span> <span data-ttu-id="c6b15-126">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c6b15-126">Optional.</span></span>|  
|[<span data-ttu-id="c6b15-127">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="c6b15-127">\<serviceCertificate></span></span>](servicecertificate.md)|<span data-ttu-id="c6b15-128">토큰을 암호화 하 고 해독 하는 데 사용 되는 인증서를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b15-128">Configures the certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="c6b15-129">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c6b15-129">Optional.</span></span>|  
|[<span data-ttu-id="c6b15-130">\<wsFederation></span><span class="sxs-lookup"><span data-stu-id="c6b15-130">\<wsFederation></span></span>](wsfederation.md)|<span data-ttu-id="c6b15-131">WS-FEDERATION 인증 모듈 (WSFAM)을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b15-131">Configures the WS-Federation Authentication Module (WSFAM).</span></span> <span data-ttu-id="c6b15-132">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c6b15-132">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c6b15-133">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c6b15-133">Parent Elements</span></span>  
  
|<span data-ttu-id="c6b15-134">요소</span><span class="sxs-lookup"><span data-stu-id="c6b15-134">Element</span></span>|<span data-ttu-id="c6b15-135">설명</span><span class="sxs-lookup"><span data-stu-id="c6b15-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c6b15-136">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="c6b15-136">\<system.identityModel.services></span></span>](system-identitymodel-services.md)|<span data-ttu-id="c6b15-137">WS-FEDERATION 프로토콜을 사용 하는 인증에 대 한 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="c6b15-137">Configuration section for authentication using the WS-Federation protocol.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6b15-138">설명</span><span class="sxs-lookup"><span data-stu-id="c6b15-138">Remarks</span></span>  
 <span data-ttu-id="c6b15-139">FederationConfiguration \<> 요소는 두 가지 시나리오에 대 한 설정을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b15-139">The \<federationConfiguration> element provides settings in two different scenarios:</span></span>  
  
- <span data-ttu-id="c6b15-140">수동 웹 응용 프로그램에서 ws-federation을 사용 하는 경우 요소에는 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (wsfam) <xref:System.IdentityModel.Services.SessionAuthenticationModule> 및 (SAM)을 구성 하는 설정이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6b15-140">When using WS-Federation in a passive Web application, the element contains settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span> <span data-ttu-id="c6b15-141">또한 보안 토큰 처리기 및 인증서를 구성 하는 데 사용 되는 id 구성과 클레임 권한 부여 관리자 및 클레임 인증 관리자와 같은 구성 요소를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b15-141">It also references the identity configuration to be used to configure security token handlers and certificates, and components like the claims authorization manager and the claims authentication manager.</span></span>  
  
- <span data-ttu-id="c6b15-142"><xref:System.IdentityModel.Services.ClaimsPrincipalPermission> 또는 클래스를 사용 하 여 코드에서 클레임 기반 액세스 제어를 제공 하는 경우 요소는 인증을 수행 하는 데 사용 되는 클레임 권한 부여 관리자 및 정책을 구성 하는 id 구성을 참조 합니다. <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> 결정.</span><span class="sxs-lookup"><span data-stu-id="c6b15-142">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the element references the identity configuration that configures the claims authorization manager and policy that is used to make authorization decisions.</span></span> <span data-ttu-id="c6b15-143">이는 수동 웹 시나리오가 아닌 시나리오 에서도 마찬가지입니다. 예를 들어 WCF (Windows Communication Foundation) 응용 프로그램 또는 웹 기반이 아닌 응용 프로그램이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6b15-143">This is true, even in scenarios that are not passive Web scenarios; for example, Windows Communication Foundation (WCF) applications or an application that is not Web-based.</span></span> <span data-ttu-id="c6b15-144">응용 프로그램이 수동 웹 응용 프로그램이 아닌 경우, `<federationConfiguration>` [ \<](claimsauthorizationmanager.md) 요소에서 참조 하는 id 구성의 claimsAuthorizationManager > 요소와 자식 정책 요소 (있는 경우)는 유일한 설정입니다. 적용.</span><span class="sxs-lookup"><span data-stu-id="c6b15-144">If the application is not a passive Web application, the [\<claimsAuthorizationManager>](claimsauthorizationmanager.md) element (and its child policy elements, if present) of the identity configuration referenced by the `<federationConfiguration>` element are the only settings applied.</span></span> <span data-ttu-id="c6b15-145">다른 특성은 모두 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6b15-145">All others are ignored.</span></span>  
  
 <span data-ttu-id="c6b15-146">시나리오에 관계 없이 런타임은 기본 페더레이션 구성을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b15-146">Regardless of the scenario, the runtime loads the default federation configuration.</span></span> <span data-ttu-id="c6b15-147">동작은 다음과 같이 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6b15-147">The behavior is defined as follows:</span></span>  
  
1. <span data-ttu-id="c6b15-148">`<federationConfiguration>` 요소가 없는 경우 런타임은 페더레이션 구성을 만들고 기본값을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="c6b15-148">If there is no `<federationConfiguration>` element present, the runtime creates a federation configuration and populates it with default values.</span></span> <span data-ttu-id="c6b15-149">이 기본 페더레이션 구성에서는 기본 id 구성을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b15-149">This default federation configuration will reference the default identity configuration.</span></span>  
  
2. <span data-ttu-id="c6b15-150">단일 `<federationConfiguration>` 요소가 있으면 이름이 지정 되었는지 아니면 이름이 지정 되지 않은 경우에 관계 없이 기본 페더레이션 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="c6b15-150">If a single `<federationConfiguration>` element is present, it is the default federation configuration regardless of whether it is named or unnamed.</span></span> <span data-ttu-id="c6b15-151">해당 `identityConfiguration` 특성이 지정 된 경우 명명 된 id 구성이 참조 되 고, 그렇지 않으면 기본 id 구성이 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6b15-151">If its `identityConfiguration` attribute is specified, the named identity configuration is referenced; otherwise, the default identity configuration is referenced.</span></span>  
  
3. <span data-ttu-id="c6b15-152">명명 되지 않은 `<federationConfiguration>` 요소가 있으면 기본 페더레이션 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="c6b15-152">If an unnamed `<federationConfiguration>` element is present, it is the default federation configuration.</span></span> <span data-ttu-id="c6b15-153">해당 `identityConfiguration` 특성이 지정 된 경우 명명 된 id 구성이 참조 되 고, 그렇지 않으면 기본 id 구성이 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6b15-153">If its `identityConfiguration` attribute is specified, the named identity configuration is referenced; otherwise, the default identity configuration is referenced.</span></span>  
  
4. <span data-ttu-id="c6b15-154">명명 `<federationConfiguration>` 된 요소를 여러 개 포함 하 고 `<federationConfiguration>` 명명 되지 않은 요소가 없으면 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6b15-154">If multiple named `<federationConfiguration>` elements are present and no unnamed `<federationConfiguration>` element is present, an exception is thrown.</span></span>  
  
 <span data-ttu-id="c6b15-155">일반적으로 하나의 `<federationConfiguration>` 섹션만 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6b15-155">Typically, only a single `<federationConfiguration>` section is defined.</span></span> <span data-ttu-id="c6b15-156">이 섹션은 기본 페더레이션 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="c6b15-156">This section is the default federation configuration.</span></span> <span data-ttu-id="c6b15-157">고유 하 게 명명 `<federationConfiguration>` 된 여러 요소를 지정할 수 있습니다. 그러나이 경우 명명 되지 않은 요소 이외의 페더레이션 구성을 로드 하려는 경우에는에 대 한 처리기를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b15-157">You may specify multiple, uniquely-named `<federationConfiguration>` elements; however, in this case, if you want to load a federation configuration other than the unnamed one, you must provide a handler for the.</span></span> <span data-ttu-id="c6b15-158"><xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated>이벤트를 처리 하 <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> 고 처리기 <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> 내의 속성을 구성 파일에 있는 해당 `<federationConfiguration>` 요소의 값으로 초기화 된 개체로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b15-158"><xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated> event and set the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> property inside the handler to a <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> object initialized with values from the appropriate `<federationConfiguration>` element in the configuration file.</span></span>  
  
 <span data-ttu-id="c6b15-159">합니다 `<federationConfiguration>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="c6b15-159">The `<federationConfiguration>` element is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> class.</span></span> <span data-ttu-id="c6b15-160">구성 개체 자체는 <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> 클래스로 표현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6b15-160">The configuration object itself is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> class.</span></span> <span data-ttu-id="c6b15-161">단일 <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> 인스턴스가 <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> 속성에 대해 설정 되 고 응용 프로그램에 대 한 페더레이션된 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b15-161">A single <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> instance is set on the <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> property and provides federated configuration for the application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6b15-162">예제</span><span class="sxs-lookup"><span data-stu-id="c6b15-162">Example</span></span>  
 <span data-ttu-id="c6b15-163">다음 XML에서는 wsfam에 대 한 설정을 지정 하 고 SAM에서 기본 쿠키 처리기 ( `<federationConfiguration>` <xref:System.IdentityModel.Services.ChunkedCookieHandler> 클래스의 인스턴스)를 사용 하도록 지정 하는 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c6b15-163">The following XML shows a `<federationConfiguration>` element that specifies settings for the WSFAM and specifies that the default cookie handler (an instance of the <xref:System.IdentityModel.Services.ChunkedCookieHandler> class) be used by the SAM.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="c6b15-164">이 예제에서는 HTTPS를 사용 하는 데 쿠키 처리기와 WSFAM이 모두 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c6b15-164">In this example, neither the cookie handler nor WSFAM are required to use HTTPS.</span></span> <span data-ttu-id="c6b15-165">`requireHttps` 이는 `<wsFederation>` 요소의 특성과의`<cookieHandlerElement>` 특성이 이기 때문입니다. `false` `requireSsl`</span><span class="sxs-lookup"><span data-stu-id="c6b15-165">This is because the `requireHttps` attribute on the `<wsFederation>` element and the `requireSsl` attribute on the `<cookieHandlerElement>` are `false`.</span></span> <span data-ttu-id="c6b15-166">이러한 설정은 보안 위험을 초래할 수 있으므로 대부분의 프로덕션 환경에는 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c6b15-166">These settings are not recommended for most production environments as they may present a security risk.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c6b15-167">참고자료</span><span class="sxs-lookup"><span data-stu-id="c6b15-167">See also</span></span>

- <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>
- <xref:System.IdentityModel.Services.SessionAuthenticationModule>
- <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>
- [<span data-ttu-id="c6b15-168">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="c6b15-168">\<identityConfiguration></span></span>](identityconfiguration.md)
