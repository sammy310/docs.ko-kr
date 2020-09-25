---
title: <federationConfiguration>
ms.date: 03/30/2017
ms.assetid: 8b14054c-6d07-46ab-ab58-03f14beac0f2
author: BrucePerlerMS
ms.openlocfilehash: 39e96a161a2e75d5f00b73f6b08b1e4a0c109aee
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201358"
---
# \<federationConfiguration>

<span data-ttu-id="dfffb-101"><xref:System.IdentityModel.Services.WSFederationAuthenticationModule>Ws-federation 프로토콜을 통해 페더레이션된 인증을 사용 하는 경우 (wsfam) 및 <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM)을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfffb-101">Configures the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) when using federated authentication through the WS-Federation protocol.</span></span> <span data-ttu-id="dfffb-102"><xref:System.Security.Claims.ClaimsAuthorizationManager>또는 클래스를 사용 하 여 <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> 클레임 기반 액세스 제어를 제공 하는 경우를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfffb-102">Configures the <xref:System.Security.Claims.ClaimsAuthorizationManager> when using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<federationConfiguration>**  
  
## <a name="syntax"></a><span data-ttu-id="dfffb-103">구문</span><span class="sxs-lookup"><span data-stu-id="dfffb-103">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dfffb-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="dfffb-104">Attributes and Elements</span></span>  

 <span data-ttu-id="dfffb-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dfffb-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dfffb-106">특성</span><span class="sxs-lookup"><span data-stu-id="dfffb-106">Attributes</span></span>  
  
|<span data-ttu-id="dfffb-107">attribute</span><span class="sxs-lookup"><span data-stu-id="dfffb-107">Attribute</span></span>|<span data-ttu-id="dfffb-108">Description</span><span class="sxs-lookup"><span data-stu-id="dfffb-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dfffb-109">name</span><span class="sxs-lookup"><span data-stu-id="dfffb-109">name</span></span>|<span data-ttu-id="dfffb-110">이 페더레이션 구성 요소의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="dfffb-110">The name of this federation configuration element.</span></span> <span data-ttu-id="dfffb-111">이 특성은 주로 이후 프로토콜에 대 한 확장성 지점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfffb-111">This attribute primarily provides an extensibility point for future protocols.</span></span> <span data-ttu-id="dfffb-112">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="dfffb-112">Optional.</span></span>|  
|<span data-ttu-id="dfffb-113">identityConfigurationName</span><span class="sxs-lookup"><span data-stu-id="dfffb-113">identityConfigurationName</span></span>|<span data-ttu-id="dfffb-114">사용할 요소에 지정 된 id 구성 섹션의 이름입니다 [\<identityConfiguration>](identityconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="dfffb-114">The name of the identity configuration section as specified in an [\<identityConfiguration>](identityconfiguration.md) element to use.</span></span> <span data-ttu-id="dfffb-115">이 특성을 지정 하지 않으면 기본 id 구성 섹션이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfffb-115">If this attribute is not specified, the default identity configuration section is used.</span></span> <span data-ttu-id="dfffb-116">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="dfffb-116">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dfffb-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="dfffb-117">Child Elements</span></span>  
  
|<span data-ttu-id="dfffb-118">요소</span><span class="sxs-lookup"><span data-stu-id="dfffb-118">Element</span></span>|<span data-ttu-id="dfffb-119">설명</span><span class="sxs-lookup"><span data-stu-id="dfffb-119">Description</span></span>|  
|-------------|-----------------|  
|[\<cookieHandler>](cookiehandler.md)|<span data-ttu-id="dfffb-120">SAM에서 사용 하는 쿠키 처리기를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfffb-120">Configures the cookie handler used by the SAM.</span></span> <span data-ttu-id="dfffb-121">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="dfffb-121">Optional.</span></span>|  
|[\<serviceCertificate>](servicecertificate.md)|<span data-ttu-id="dfffb-122">토큰을 암호화 하 고 해독 하는 데 사용 되는 인증서를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfffb-122">Configures the certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="dfffb-123">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="dfffb-123">Optional.</span></span>|  
|[\<wsFederation>](wsfederation.md)|<span data-ttu-id="dfffb-124">WS-FEDERATION 인증 모듈 (WSFAM)을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfffb-124">Configures the WS-Federation Authentication Module (WSFAM).</span></span> <span data-ttu-id="dfffb-125">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="dfffb-125">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dfffb-126">부모 요소</span><span class="sxs-lookup"><span data-stu-id="dfffb-126">Parent Elements</span></span>  
  
|<span data-ttu-id="dfffb-127">요소</span><span class="sxs-lookup"><span data-stu-id="dfffb-127">Element</span></span>|<span data-ttu-id="dfffb-128">설명</span><span class="sxs-lookup"><span data-stu-id="dfffb-128">Description</span></span>|  
|-------------|-----------------|  
|[\<system.identityModel.services>](system-identitymodel-services.md)|<span data-ttu-id="dfffb-129">WS-FEDERATION 프로토콜을 사용 하는 인증에 대 한 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="dfffb-129">Configuration section for authentication using the WS-Federation protocol.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dfffb-130">설명</span><span class="sxs-lookup"><span data-stu-id="dfffb-130">Remarks</span></span>  

 <span data-ttu-id="dfffb-131">\<federationConfiguration>요소는 다음과 같은 두 가지 시나리오에서 설정을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfffb-131">The \<federationConfiguration> element provides settings in two different scenarios:</span></span>  
  
- <span data-ttu-id="dfffb-132">수동 웹 응용 프로그램에서 WS-FEDERATION을 사용 하는 경우 요소에는 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (wsfam) 및 (SAM)을 구성 하는 설정이 포함 <xref:System.IdentityModel.Services.SessionAuthenticationModule> 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfffb-132">When using WS-Federation in a passive Web application, the element contains settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span> <span data-ttu-id="dfffb-133">또한 보안 토큰 처리기 및 인증서를 구성 하는 데 사용 되는 id 구성과 클레임 권한 부여 관리자 및 클레임 인증 관리자와 같은 구성 요소를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfffb-133">It also references the identity configuration to be used to configure security token handlers and certificates, and components like the claims authorization manager and the claims authentication manager.</span></span>  
  
- <span data-ttu-id="dfffb-134">또는 클래스를 사용 하 여 <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> 코드에서 클레임 기반 액세스 제어를 제공 하는 경우 요소는 권한 부여를 결정 하는 데 사용 되는 클레임 권한 부여 관리자 및 정책을 구성 하는 id 구성을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfffb-134">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the element references the identity configuration that configures the claims authorization manager and policy that is used to make authorization decisions.</span></span> <span data-ttu-id="dfffb-135">이는 수동 웹 시나리오가 아닌 시나리오 에서도 마찬가지입니다. 예를 들어 WCF (Windows Communication Foundation) 응용 프로그램 또는 웹 기반이 아닌 응용 프로그램이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfffb-135">This is true, even in scenarios that are not passive Web scenarios; for example, Windows Communication Foundation (WCF) applications or an application that is not Web-based.</span></span> <span data-ttu-id="dfffb-136">응용 프로그램이 수동 웹 응용 프로그램이 아닌 경우 [\<claimsAuthorizationManager>](claimsauthorizationmanager.md) 요소가 참조 하는 id 구성의 요소 및 자식 정책 요소 (있는 경우) `<federationConfiguration>` 만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfffb-136">If the application is not a passive Web application, the [\<claimsAuthorizationManager>](claimsauthorizationmanager.md) element (and its child policy elements, if present) of the identity configuration referenced by the `<federationConfiguration>` element are the only settings applied.</span></span> <span data-ttu-id="dfffb-137">다른 특성은 모두 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfffb-137">All others are ignored.</span></span>  
  
 <span data-ttu-id="dfffb-138">시나리오에 관계 없이 런타임은 기본 페더레이션 구성을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfffb-138">Regardless of the scenario, the runtime loads the default federation configuration.</span></span> <span data-ttu-id="dfffb-139">동작은 다음과 같이 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfffb-139">The behavior is defined as follows:</span></span>  
  
1. <span data-ttu-id="dfffb-140">요소가 없는 경우 `<federationConfiguration>` 런타임은 페더레이션 구성을 만들고 기본값을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="dfffb-140">If there is no `<federationConfiguration>` element present, the runtime creates a federation configuration and populates it with default values.</span></span> <span data-ttu-id="dfffb-141">이 기본 페더레이션 구성에서는 기본 id 구성을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfffb-141">This default federation configuration will reference the default identity configuration.</span></span>  
  
2. <span data-ttu-id="dfffb-142">단일 요소가 있으면 `<federationConfiguration>` 이름이 지정 되었는지 아니면 이름이 지정 되지 않은 경우에 관계 없이 기본 페더레이션 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="dfffb-142">If a single `<federationConfiguration>` element is present, it is the default federation configuration regardless of whether it is named or unnamed.</span></span> <span data-ttu-id="dfffb-143">해당 `identityConfiguration` 특성이 지정 된 경우 명명 된 id 구성이 참조 되 고, 그렇지 않으면 기본 id 구성이 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfffb-143">If its `identityConfiguration` attribute is specified, the named identity configuration is referenced; otherwise, the default identity configuration is referenced.</span></span>  
  
3. <span data-ttu-id="dfffb-144">명명 되지 않은 `<federationConfiguration>` 요소가 있으면 기본 페더레이션 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="dfffb-144">If an unnamed `<federationConfiguration>` element is present, it is the default federation configuration.</span></span> <span data-ttu-id="dfffb-145">해당 `identityConfiguration` 특성이 지정 된 경우 명명 된 id 구성이 참조 되 고, 그렇지 않으면 기본 id 구성이 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfffb-145">If its `identityConfiguration` attribute is specified, the named identity configuration is referenced; otherwise, the default identity configuration is referenced.</span></span>  
  
4. <span data-ttu-id="dfffb-146">명명 된 요소를 여러 개 `<federationConfiguration>` 포함 하 고 명명 되지 않은 `<federationConfiguration>` 요소가 없으면 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfffb-146">If multiple named `<federationConfiguration>` elements are present and no unnamed `<federationConfiguration>` element is present, an exception is thrown.</span></span>  
  
 <span data-ttu-id="dfffb-147">일반적으로 하나의 `<federationConfiguration>` 섹션만 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfffb-147">Typically, only a single `<federationConfiguration>` section is defined.</span></span> <span data-ttu-id="dfffb-148">이 섹션은 기본 페더레이션 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="dfffb-148">This section is the default federation configuration.</span></span> <span data-ttu-id="dfffb-149">고유 하 게 명명 된 여러 요소를 지정할 수 있습니다 `<federationConfiguration>` . 그러나이 경우 명명 되지 않은 요소 이외의 페더레이션 구성을 로드 하려는 경우에는에 대 한 처리기를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfffb-149">You may specify multiple, uniquely-named `<federationConfiguration>` elements; however, in this case, if you want to load a federation configuration other than the unnamed one, you must provide a handler for the.</span></span> <span data-ttu-id="dfffb-150"><xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated> 이벤트를 처리 하 고 <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> 처리기 내의 속성을 <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> `<federationConfiguration>` 구성 파일에 있는 해당 요소의 값으로 초기화 된 개체로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfffb-150"><xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated> event and set the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> property inside the handler to a <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> object initialized with values from the appropriate `<federationConfiguration>` element in the configuration file.</span></span>  
  
 <span data-ttu-id="dfffb-151">합니다 `<federationConfiguration>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="dfffb-151">The `<federationConfiguration>` element is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> class.</span></span> <span data-ttu-id="dfffb-152">구성 개체 자체는 클래스로 표현 됩니다 <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> .</span><span class="sxs-lookup"><span data-stu-id="dfffb-152">The configuration object itself is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> class.</span></span> <span data-ttu-id="dfffb-153">단일 <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> 인스턴스가 속성에 대해 설정 되 <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> 고 응용 프로그램에 대 한 페더레이션된 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfffb-153">A single <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> instance is set on the <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> property and provides federated configuration for the application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dfffb-154">예제</span><span class="sxs-lookup"><span data-stu-id="dfffb-154">Example</span></span>  

 <span data-ttu-id="dfffb-155">다음 XML에서는 `<federationConfiguration>` WSFAM에 대 한 설정을 지정 하 고 SAM에서 기본 쿠키 처리기 (클래스의 인스턴스)를 사용 하도록 지정 하는 요소를 보여 줍니다 <xref:System.IdentityModel.Services.ChunkedCookieHandler> .</span><span class="sxs-lookup"><span data-stu-id="dfffb-155">The following XML shows a `<federationConfiguration>` element that specifies settings for the WSFAM and specifies that the default cookie handler (an instance of the <xref:System.IdentityModel.Services.ChunkedCookieHandler> class) be used by the SAM.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="dfffb-156">이 예제에서는 HTTPS를 사용 하는 데 쿠키 처리기와 WSFAM이 모두 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dfffb-156">In this example, neither the cookie handler nor WSFAM are required to use HTTPS.</span></span> <span data-ttu-id="dfffb-157">이는 요소의 특성과의 특성이 이기 때문입니다 `requireHttps` `<wsFederation>` `requireSsl` `<cookieHandlerElement>` `false` .</span><span class="sxs-lookup"><span data-stu-id="dfffb-157">This is because the `requireHttps` attribute on the `<wsFederation>` element and the `requireSsl` attribute on the `<cookieHandlerElement>` are `false`.</span></span> <span data-ttu-id="dfffb-158">이러한 설정은 보안 위험을 초래할 수 있으므로 대부분의 프로덕션 환경에는 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dfffb-158">These settings are not recommended for most production environments as they may present a security risk.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dfffb-159">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dfffb-159">See also</span></span>

- <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>
- <xref:System.IdentityModel.Services.SessionAuthenticationModule>
- <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>
- [\<identityConfiguration>](identityconfiguration.md)
