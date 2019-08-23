---
title: <identityConfiguration>
ms.date: 03/30/2017
ms.assetid: 1db76253-07da-447b-9e7a-3705c7228cf4
author: BrucePerlerMS
ms.openlocfilehash: 9f5e0c5ded3d750a1102492c7a506e6d5643b2d4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942745"
---
# <a name="identityconfiguration"></a><span data-ttu-id="efa83-101">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="efa83-101">\<identityConfiguration></span></span>

<span data-ttu-id="efa83-102">서비스 수준 id 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-102">Specifies service-level identity settings.</span></span>

 <span data-ttu-id="efa83-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="efa83-103">\<system.identityModel></span></span>\
<span data-ttu-id="efa83-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="efa83-104">\<identityConfiguration></span></span>

## <a name="syntax"></a><span data-ttu-id="efa83-105">구문</span><span class="sxs-lookup"><span data-stu-id="efa83-105">Syntax</span></span>

```xml
<system.identityModel>
  <identityConfiguration
      name=xs:string
      saveBootstrapContext=xs:boolean>
      maximumClockSkew=TimeSpan >
  </identityConfiguration>
</system.identityModel>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="efa83-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="efa83-106">Attributes and Elements</span></span>

<span data-ttu-id="efa83-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="efa83-108">특성</span><span class="sxs-lookup"><span data-stu-id="efa83-108">Attributes</span></span>

|<span data-ttu-id="efa83-109">특성</span><span class="sxs-lookup"><span data-stu-id="efa83-109">Attribute</span></span>|<span data-ttu-id="efa83-110">설명</span><span class="sxs-lookup"><span data-stu-id="efa83-110">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="efa83-111">name</span><span class="sxs-lookup"><span data-stu-id="efa83-111">name</span></span>|<span data-ttu-id="efa83-112">Id 구성 섹션의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-112">The name of the identity configuration section.</span></span> <span data-ttu-id="efa83-113">이 이름을 사용 하 여 특정 구성 섹션을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-113">You can use this name to reference a specific configuration section.</span></span> <span data-ttu-id="efa83-114">특성을 `name` 지정 하지 않으면 섹션에서 기본 구성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-114">If no `name` attribute is specified, the section defines the default configuration.</span></span> <span data-ttu-id="efa83-115">기본 구성은 항상 수동 페더레이션 시나리오에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-115">The default configuration is always used for passive federation scenarios.</span></span> <span data-ttu-id="efa83-116">자세한 내용은 [ \<federationConfiguration >](federationconfiguration.md) 요소를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="efa83-116">For more information, see the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>|
|<span data-ttu-id="efa83-117">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="efa83-117">saveBootstrapContext</span></span>|<span data-ttu-id="efa83-118">부트스트랩 토큰이 세션 토큰에 포함 되어야 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-118">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="efa83-119">`saveBootstrapContext` [SecurityTokenHandlerConfiguration > 요소에 대 한 특성을 설정 하 여 토큰 처리기 컬렉션에서 값을 설정할 수도 있습니다. \<](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="efa83-119">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) element.</span></span> <span data-ttu-id="efa83-120">토큰 처리기 컬렉션에 설정 된 값은 서비스에 설정 된 값을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-120">A value set on the token handler collection overrides the value set on the service.</span></span>|
|<span data-ttu-id="efa83-121">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="efa83-121">maximumClockSkew</span></span>|<span data-ttu-id="efa83-122">허용 되는 최대 클록 오차를 지정 하는입니다.<xref:System.TimeSpan></span><span class="sxs-lookup"><span data-stu-id="efa83-122">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="efa83-123">로그인 세션이 만료 시간 유효성 검사와 같은 시간에 민감한 작업을 수행할 때 허용 되는 최대 클럭 오차를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-123">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="efa83-124">기본값은 5 분 "00:05:00"입니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-124">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="efa83-125">값을 지정 <xref:System.TimeSpan> 하는 방법에 대 한 자세한 내용은 [Timespan 값](../windows-workflow-foundation/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="efa83-125">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="efa83-126">`maximumClockSkew` [SecurityTokenHandlerConfiguration > 요소에 대 한 특성을 설정 하 여 토큰 처리기 컬렉션에서 최대 클록 오차를 설정할 수도 있습니다. \<](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="efa83-126">The maximum clock skew may also be set on a token handler collection by setting the `maximumClockSkew` attribute on the [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) element.</span></span> <span data-ttu-id="efa83-127">토큰 처리기 컬렉션에 설정 된 값은 서비스에 설정 된 값을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-127">A value set on the token handler collection overrides the value set on the service.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="efa83-128">자식 요소</span><span class="sxs-lookup"><span data-stu-id="efa83-128">Child Elements</span></span>

|<span data-ttu-id="efa83-129">요소</span><span class="sxs-lookup"><span data-stu-id="efa83-129">Element</span></span>|<span data-ttu-id="efa83-130">Description</span><span class="sxs-lookup"><span data-stu-id="efa83-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="efa83-131">\<caches></span><span class="sxs-lookup"><span data-stu-id="efa83-131">\<caches></span></span>](caches.md)|<span data-ttu-id="efa83-132">세션 토큰 및 토큰 재생 검색에 사용 되는 캐시를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-132">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="efa83-133">는 서비스 수준 또는 보안 토큰 처리기 컬렉션에서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-133">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="efa83-134">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-134">Optional.</span></span>|
|[<span data-ttu-id="efa83-135">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="efa83-135">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="efa83-136">토큰 처리기에서 인증서의 유효성을 검사 하는 데 사용 하는 설정을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-136">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="efa83-137">는 서비스 수준 또는 보안 토큰 처리기 컬렉션에서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-137">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="efa83-138">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-138">Optional.</span></span>|
|[<span data-ttu-id="efa83-139">\<claimsAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="efa83-139">\<claimsAuthenticationManager></span></span>](claimsauthenticationmanager.md)|<span data-ttu-id="efa83-140">들어오는 클레임에 대 한 클레임 인증 관리자를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-140">Registers a claims authentication manager for the incoming claims.</span></span> <span data-ttu-id="efa83-141">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-141">Optional.</span></span>|
|[<span data-ttu-id="efa83-142">\<claimsAuthorizationManager></span><span class="sxs-lookup"><span data-stu-id="efa83-142">\<claimsAuthorizationManager></span></span>](claimsauthorizationmanager.md)|<span data-ttu-id="efa83-143">들어오는 클레임에 대 한 클레임 권한 부여 관리자를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-143">Registers a claims authorization manager for the incoming claims.</span></span> <span data-ttu-id="efa83-144">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-144">Optional.</span></span>|
|[<span data-ttu-id="efa83-145">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="efa83-145">\<claimTypeRequired></span></span>](claimtyperequired.md)|<span data-ttu-id="efa83-146">들어오는 보안 토큰에 대 한 필수 클레임 집합을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-146">Specifies the set of required claims for incoming security tokens.</span></span> <span data-ttu-id="efa83-147">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-147">Optional.</span></span>|
|[<span data-ttu-id="efa83-148">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="efa83-148">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="efa83-149">보안 토큰 처리기의 컬렉션을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-149">Specifies a collection of security token handlers.</span></span> <span data-ttu-id="efa83-150">0 개 이상의 보안 토큰 처리기 컬렉션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-150">Zero or more collections of security token handlers can be specified.</span></span> <span data-ttu-id="efa83-151">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-151">Optional.</span></span>|
|[<span data-ttu-id="efa83-152">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="efa83-152">\<tokenReplayDetection></span></span>](tokenreplaydetection.md)|<span data-ttu-id="efa83-153">토큰 재생 검색을 사용 하도록 설정 하 고 토큰의 만료 시간을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-153">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="efa83-154">는 서비스 수준 또는 보안 토큰 처리기 컬렉션에서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-154">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="efa83-155">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-155">Optional.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="efa83-156">부모 요소</span><span class="sxs-lookup"><span data-stu-id="efa83-156">Parent Elements</span></span>

|<span data-ttu-id="efa83-157">요소</span><span class="sxs-lookup"><span data-stu-id="efa83-157">Element</span></span>|<span data-ttu-id="efa83-158">Description</span><span class="sxs-lookup"><span data-stu-id="efa83-158">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="efa83-159">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="efa83-159">\<system.identityModel></span></span>](system-identitymodel.md)|<span data-ttu-id="efa83-160">응용 프로그램에서 WIF (Windows Identity Foundation) 옵션을 사용 하도록 구성 하는 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-160">Provides configuration for enabling Windows Identity Foundation (WIF) options in applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="efa83-161">설명</span><span class="sxs-lookup"><span data-stu-id="efa83-161">Remarks</span></span>

<span data-ttu-id="efa83-162">각각 고유한 이름을 가진 여러 id 구성이 정의 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-162">Multiple identity configurations may be defined, each with a unique name.</span></span> <span data-ttu-id="efa83-163">동작은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-163">The behavior is as follows:</span></span>

1. <span data-ttu-id="efa83-164">요소가 지정 `<identityConfiguration>` 되지 않은 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-164">If no `<identityConfiguration>` element is specified.</span></span> <span data-ttu-id="efa83-165">기본 id 구성은 런타임에 만들어지며 기본값으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-165">A default identity configuration is created at runtime and populated with default values.</span></span>

2. <span data-ttu-id="efa83-166">단일 `<identityConfiguration>` 요소가 지정 된 경우</span><span class="sxs-lookup"><span data-stu-id="efa83-166">If a single `<identityConfiguration>` element is specified.</span></span> <span data-ttu-id="efa83-167">기본 id 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-167">It is the default identity configuration.</span></span> <span data-ttu-id="efa83-168">이름이 지정 되거나 이름이 지정 되지 않은 경우에는 중요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-168">It does not matter whether it is named or unnamed.</span></span>

3. <span data-ttu-id="efa83-169">여러 `<identityConfiguration>` 요소가 지정 된 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-169">If multiple `<identityConfiguration>` elements are specified.</span></span> <span data-ttu-id="efa83-170">명명 되지 않은 요소는 기본 id 구성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-170">The unnamed element specifies the default identity configuration.</span></span> <span data-ttu-id="efa83-171">여러 `<identityConfiguration>` 요소를 지정 하는 경우 둘 중 하나를 명명 되지 않은 상태로 지정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-171">It is recommended that when you specify multiple `<identityConfiguration>` elements, one of them should be unnamed.</span></span>

> [!WARNING]
> <span data-ttu-id="efa83-172">여러 `<identityConfiguration>` 요소를 지정 하는 경우 그 중 하나에 이름이 지정 되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-172">If you specify multiple `<identityConfiguration>` elements, one of them should be unnamed.</span></span> <span data-ttu-id="efa83-173">명명 되지 않은 요소는 기본 id 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-173">The unnamed element will be the default identity configuration.</span></span>

 <span data-ttu-id="efa83-174">`<identityConfiguration>` 요소에 지정 된 설정 중 일부는 보안 토큰 처리기 컬렉션의 설정 또는 개별 보안 토큰 처리기의 설정에 의해 재정의 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-174">Some of the settings specified in the `<identityConfiguration>` element can be overridden by settings on a security token handler collection or by settings on individual security token handlers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="efa83-175">또는 클래스를 사용 하 여 `<federationConfiguration>` 코드에서 클레임 기반 액세스 제어를 제공 하는 경우 요소에서 참조 하는 id 구성은 클레임 권한 부여 관리자 및 다음을 수행 하는 데 사용 되는 정책을 구성 합니다. <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> 권한 부여 결정.</span><span class="sxs-lookup"><span data-stu-id="efa83-175">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the identity configuration that is referenced by the `<federationConfiguration>` element configures the claims authorization manager and policy that is used to make authorization decisions.</span></span> <span data-ttu-id="efa83-176">이는 Windows Communication Foundation (WCF) 응용 프로그램 또는 웹 기반이 아닌 응용 프로그램 등 수동 웹 시나리오가 아닌 시나리오 에서도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-176">This is true, even in scenarios that are not passive Web scenarios, for example Windows Communication Foundation (WCF) applications or an application that is not Web-based.</span></span> <span data-ttu-id="efa83-177">응용 프로그램이 수동 웹 응용 프로그램이 [ \<](claimsauthorizationmanager.md) 아닌 경우 참조 되는 id 구성의 claimsAuthorizationManager > 요소와 자식 정책 요소 (있는 경우)만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-177">If the application is not a passive Web application, the [\<claimsAuthorizationManager>](claimsauthorizationmanager.md) element (and its child policy elements, if present) of the referenced identity configuration are the only settings applied.</span></span> <span data-ttu-id="efa83-178">다른 모든 설정은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-178">All other settings are ignored.</span></span> <span data-ttu-id="efa83-179">자세한 내용은 [ \<federationConfiguration >](federationconfiguration.md) 요소를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="efa83-179">For more information, see the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>

<span data-ttu-id="efa83-180">합니다 `<identityConfiguration>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Configuration.IdentityConfigurationElement> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-180">The `<identityConfiguration>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityConfigurationElement> class.</span></span> <span data-ttu-id="efa83-181">Id 구성 섹션은 <xref:System.IdentityModel.Configuration.IdentityConfiguration> 클래스로 표현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-181">An identity configuration section is represented by the <xref:System.IdentityModel.Configuration.IdentityConfiguration> class.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="efa83-182">다음 요소를 `<identityConfiguration>` 요소의 자식 요소로 지정 하는 기능은 이전 버전과의 호환성을 위해 계속 지원 되지만 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-182">Specifying the following elements as child elements of the `<identityConfiguration>` element has been deprecated, although the behavior is still supported for backward compatibility.</span></span> <span data-ttu-id="efa83-183">대신 이러한 요소는 [ \<securityTokenHandlerConfiguration >](securitytokenhandlerconfiguration.md) 요소 아래에 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-183">These elements should, instead, be specified under the [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) element.</span></span>
>
> - [<span data-ttu-id="efa83-184">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="efa83-184">\<audienceUris></span></span>](audienceuris.md)
> - [<span data-ttu-id="efa83-185">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="efa83-185">\<issuerNameRegistry></span></span>](issuernameregistry.md)
> - [<span data-ttu-id="efa83-186">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="efa83-186">\<issuerTokenResolver></span></span>](issuertokenresolver.md)
> - [<span data-ttu-id="efa83-187">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="efa83-187">\<serviceTokenResolver></span></span>](servicetokenresolver.md)

## <a name="example"></a><span data-ttu-id="efa83-188">예제</span><span class="sxs-lookup"><span data-stu-id="efa83-188">Example</span></span>

<span data-ttu-id="efa83-189">다음 예에서는 "alternateConfiguration" 라는 id 구성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-189">The following example creates an identity configuration named "alternateConfiguration".</span></span> <span data-ttu-id="efa83-190">Id 구성에서는 기본 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="efa83-190">The identity configuration specifies default settings.</span></span>

```xml
<system.identityModel>
    <identityConfiguration name="alternateConfiguration"/>
</system.identityModel>
```

## <a name="see-also"></a><span data-ttu-id="efa83-191">참고자료</span><span class="sxs-lookup"><span data-stu-id="efa83-191">See also</span></span>

- <xref:System.IdentityModel.Configuration.IdentityConfiguration>
- <xref:System.IdentityModel.Configuration.IdentityConfigurationElement>
