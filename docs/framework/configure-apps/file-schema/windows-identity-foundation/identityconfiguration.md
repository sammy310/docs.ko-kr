---
description: 다음에 대해 자세히 알아보세요. <identityConfiguration>
title: <identityConfiguration>
ms.date: 03/30/2017
ms.assetid: 1db76253-07da-447b-9e7a-3705c7228cf4
author: BrucePerlerMS
ms.openlocfilehash: 987dfb006984f757ad117157e915f1909ab3a8c2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99773409"
---
# \<identityConfiguration>

<span data-ttu-id="bc0d2-102">서비스 수준 id 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-102">Specifies service-level identity settings.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<identityConfiguration>**  

## <a name="syntax"></a><span data-ttu-id="bc0d2-103">구문</span><span class="sxs-lookup"><span data-stu-id="bc0d2-103">Syntax</span></span>

```xml
<system.identityModel>
  <identityConfiguration
      name=xs:string
      saveBootstrapContext=xs:boolean>
      maximumClockSkew=TimeSpan >
  </identityConfiguration>
</system.identityModel>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bc0d2-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="bc0d2-104">Attributes and Elements</span></span>

<span data-ttu-id="bc0d2-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-105">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="bc0d2-106">특성</span><span class="sxs-lookup"><span data-stu-id="bc0d2-106">Attributes</span></span>

|<span data-ttu-id="bc0d2-107">attribute</span><span class="sxs-lookup"><span data-stu-id="bc0d2-107">Attribute</span></span>|<span data-ttu-id="bc0d2-108">설명</span><span class="sxs-lookup"><span data-stu-id="bc0d2-108">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="bc0d2-109">name</span><span class="sxs-lookup"><span data-stu-id="bc0d2-109">name</span></span>|<span data-ttu-id="bc0d2-110">Id 구성 섹션의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-110">The name of the identity configuration section.</span></span> <span data-ttu-id="bc0d2-111">이 이름을 사용 하 여 특정 구성 섹션을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-111">You can use this name to reference a specific configuration section.</span></span> <span data-ttu-id="bc0d2-112">특성을 `name` 지정 하지 않으면 섹션에서 기본 구성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-112">If no `name` attribute is specified, the section defines the default configuration.</span></span> <span data-ttu-id="bc0d2-113">기본 구성은 항상 수동 페더레이션 시나리오에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-113">The default configuration is always used for passive federation scenarios.</span></span> <span data-ttu-id="bc0d2-114">자세한 내용은 요소를 참조 하세요 [\<federationConfiguration>](federationconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="bc0d2-114">For more information, see the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>|
|<span data-ttu-id="bc0d2-115">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="bc0d2-115">saveBootstrapContext</span></span>|<span data-ttu-id="bc0d2-116">부트스트랩 토큰이 세션 토큰에 포함 되어야 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-116">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="bc0d2-117">`saveBootstrapContext`요소에 대 한 특성을 설정 하 여 토큰 처리기 컬렉션에서 값을 설정할 수도 있습니다 [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="bc0d2-117">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) element.</span></span> <span data-ttu-id="bc0d2-118">토큰 처리기 컬렉션에 설정 된 값은 서비스에 설정 된 값을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-118">A value set on the token handler collection overrides the value set on the service.</span></span>|
|<span data-ttu-id="bc0d2-119">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="bc0d2-119">maximumClockSkew</span></span>|<span data-ttu-id="bc0d2-120"><xref:System.TimeSpan>허용 되는 최대 클록 오차를 지정 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-120">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="bc0d2-121">로그인 세션이 만료 시간 유효성 검사와 같은 시간에 민감한 작업을 수행할 때 허용 되는 최대 클럭 오차를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-121">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="bc0d2-122">기본값은 5 분 "00:05:00"입니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-122">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="bc0d2-123">값을 지정 하는 방법에 대 한 자세한 내용은 <xref:System.TimeSpan> [Timespan 값](../windows-workflow-foundation/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-123">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="bc0d2-124">`maximumClockSkew`요소에 대 한 특성을 설정 하 여 토큰 처리기 컬렉션에서 최대 클록 오차를 설정할 수도 있습니다 [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="bc0d2-124">The maximum clock skew may also be set on a token handler collection by setting the `maximumClockSkew` attribute on the [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) element.</span></span> <span data-ttu-id="bc0d2-125">토큰 처리기 컬렉션에 설정 된 값은 서비스에 설정 된 값을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-125">A value set on the token handler collection overrides the value set on the service.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="bc0d2-126">자식 요소</span><span class="sxs-lookup"><span data-stu-id="bc0d2-126">Child Elements</span></span>

|<span data-ttu-id="bc0d2-127">요소</span><span class="sxs-lookup"><span data-stu-id="bc0d2-127">Element</span></span>|<span data-ttu-id="bc0d2-128">설명</span><span class="sxs-lookup"><span data-stu-id="bc0d2-128">Description</span></span>|
|-------------|-----------------|
|[\<caches>](caches.md)|<span data-ttu-id="bc0d2-129">세션 토큰 및 토큰 재생 검색에 사용 되는 캐시를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-129">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="bc0d2-130">는 서비스 수준 또는 보안 토큰 처리기 컬렉션에서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-130">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="bc0d2-131">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-131">Optional.</span></span>|
|[\<certificateValidation>](certificatevalidation.md)|<span data-ttu-id="bc0d2-132">토큰 처리기에서 인증서의 유효성을 검사 하는 데 사용 하는 설정을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-132">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="bc0d2-133">는 서비스 수준 또는 보안 토큰 처리기 컬렉션에서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-133">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="bc0d2-134">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-134">Optional.</span></span>|
|[\<claimsAuthenticationManager>](claimsauthenticationmanager.md)|<span data-ttu-id="bc0d2-135">들어오는 클레임에 대 한 클레임 인증 관리자를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-135">Registers a claims authentication manager for the incoming claims.</span></span> <span data-ttu-id="bc0d2-136">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-136">Optional.</span></span>|
|[\<claimsAuthorizationManager>](claimsauthorizationmanager.md)|<span data-ttu-id="bc0d2-137">들어오는 클레임에 대 한 클레임 권한 부여 관리자를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-137">Registers a claims authorization manager for the incoming claims.</span></span> <span data-ttu-id="bc0d2-138">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-138">Optional.</span></span>|
|[\<claimTypeRequired>](claimtyperequired.md)|<span data-ttu-id="bc0d2-139">들어오는 보안 토큰에 대 한 필수 클레임 집합을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-139">Specifies the set of required claims for incoming security tokens.</span></span> <span data-ttu-id="bc0d2-140">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-140">Optional.</span></span>|
|[\<securityTokenHandlers>](securitytokenhandlers.md)|<span data-ttu-id="bc0d2-141">보안 토큰 처리기의 컬렉션을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-141">Specifies a collection of security token handlers.</span></span> <span data-ttu-id="bc0d2-142">0 개 이상의 보안 토큰 처리기 컬렉션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-142">Zero or more collections of security token handlers can be specified.</span></span> <span data-ttu-id="bc0d2-143">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-143">Optional.</span></span>|
|[\<tokenReplayDetection>](tokenreplaydetection.md)|<span data-ttu-id="bc0d2-144">토큰 재생 검색을 사용 하도록 설정 하 고 토큰의 만료 시간을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-144">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="bc0d2-145">는 서비스 수준 또는 보안 토큰 처리기 컬렉션에서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-145">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="bc0d2-146">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-146">Optional.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="bc0d2-147">부모 요소</span><span class="sxs-lookup"><span data-stu-id="bc0d2-147">Parent Elements</span></span>

|<span data-ttu-id="bc0d2-148">요소</span><span class="sxs-lookup"><span data-stu-id="bc0d2-148">Element</span></span>|<span data-ttu-id="bc0d2-149">설명</span><span class="sxs-lookup"><span data-stu-id="bc0d2-149">Description</span></span>|
|-------------|-----------------|
|[\<system.identityModel>](system-identitymodel.md)|<span data-ttu-id="bc0d2-150">응용 프로그램에서 WIF (Windows Identity Foundation) 옵션을 사용 하도록 구성 하는 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-150">Provides configuration for enabling Windows Identity Foundation (WIF) options in applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="bc0d2-151">설명</span><span class="sxs-lookup"><span data-stu-id="bc0d2-151">Remarks</span></span>

<span data-ttu-id="bc0d2-152">각각 고유한 이름을 가진 여러 id 구성이 정의 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-152">Multiple identity configurations may be defined, each with a unique name.</span></span> <span data-ttu-id="bc0d2-153">동작은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-153">The behavior is as follows:</span></span>

1. <span data-ttu-id="bc0d2-154">요소가 지정 되지 않은 경우 `<identityConfiguration>` 입니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-154">If no `<identityConfiguration>` element is specified.</span></span> <span data-ttu-id="bc0d2-155">기본 id 구성은 런타임에 만들어지며 기본값으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-155">A default identity configuration is created at runtime and populated with default values.</span></span>

2. <span data-ttu-id="bc0d2-156">단일 `<identityConfiguration>` 요소가 지정 된 경우</span><span class="sxs-lookup"><span data-stu-id="bc0d2-156">If a single `<identityConfiguration>` element is specified.</span></span> <span data-ttu-id="bc0d2-157">기본 id 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-157">It is the default identity configuration.</span></span> <span data-ttu-id="bc0d2-158">이름이 지정 되거나 이름이 지정 되지 않은 경우에는 중요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-158">It does not matter whether it is named or unnamed.</span></span>

3. <span data-ttu-id="bc0d2-159">여러 `<identityConfiguration>` 요소가 지정 된 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-159">If multiple `<identityConfiguration>` elements are specified.</span></span> <span data-ttu-id="bc0d2-160">명명 되지 않은 요소는 기본 id 구성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-160">The unnamed element specifies the default identity configuration.</span></span> <span data-ttu-id="bc0d2-161">여러 요소를 지정 하는 경우 `<identityConfiguration>` 둘 중 하나를 명명 되지 않은 상태로 지정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-161">It is recommended that when you specify multiple `<identityConfiguration>` elements, one of them should be unnamed.</span></span>

> [!WARNING]
> <span data-ttu-id="bc0d2-162">여러 요소를 지정 하는 경우 그 중 하나에 이름이 지정 되지 `<identityConfiguration>` 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-162">If you specify multiple `<identityConfiguration>` elements, one of them should be unnamed.</span></span> <span data-ttu-id="bc0d2-163">명명 되지 않은 요소는 기본 id 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-163">The unnamed element will be the default identity configuration.</span></span>

 <span data-ttu-id="bc0d2-164">요소에 지정 된 설정 중 일부는 `<identityConfiguration>` 보안 토큰 처리기 컬렉션의 설정 또는 개별 보안 토큰 처리기의 설정에 의해 재정의 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-164">Some of the settings specified in the `<identityConfiguration>` element can be overridden by settings on a security token handler collection or by settings on individual security token handlers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bc0d2-165">또는 클래스를 사용 하 여 <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> 코드에서 클레임 기반 액세스 제어를 제공 하는 경우 요소에서 참조 하는 id 구성은 `<federationConfiguration>` 권한 부여 관리자와 권한 부여 결정을 내리는 데 사용 되는 정책을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-165">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the identity configuration that is referenced by the `<federationConfiguration>` element configures the claims authorization manager and policy that is used to make authorization decisions.</span></span> <span data-ttu-id="bc0d2-166">이는 Windows Communication Foundation (WCF) 응용 프로그램 또는 웹 기반이 아닌 응용 프로그램 등 수동 웹 시나리오가 아닌 시나리오 에서도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-166">This is true, even in scenarios that are not passive Web scenarios, for example Windows Communication Foundation (WCF) applications or an application that is not Web-based.</span></span> <span data-ttu-id="bc0d2-167">응용 프로그램이 수동 웹 응용 프로그램이 아닌 경우 참조 되는 [\<claimsAuthorizationManager>](claimsauthorizationmanager.md) id 구성의 요소 및 자식 정책 요소 (있는 경우)만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-167">If the application is not a passive Web application, the [\<claimsAuthorizationManager>](claimsauthorizationmanager.md) element (and its child policy elements, if present) of the referenced identity configuration are the only settings applied.</span></span> <span data-ttu-id="bc0d2-168">다른 모든 설정은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-168">All other settings are ignored.</span></span> <span data-ttu-id="bc0d2-169">자세한 내용은 요소를 참조 하세요 [\<federationConfiguration>](federationconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="bc0d2-169">For more information, see the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>

<span data-ttu-id="bc0d2-170">합니다 `<identityConfiguration>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Configuration.IdentityConfigurationElement> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-170">The `<identityConfiguration>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityConfigurationElement> class.</span></span> <span data-ttu-id="bc0d2-171">Id 구성 섹션은 클래스로 표현 됩니다 <xref:System.IdentityModel.Configuration.IdentityConfiguration> .</span><span class="sxs-lookup"><span data-stu-id="bc0d2-171">An identity configuration section is represented by the <xref:System.IdentityModel.Configuration.IdentityConfiguration> class.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bc0d2-172">다음 요소를 요소의 자식 요소로 지정 하는 기능은 `<identityConfiguration>` 이전 버전과의 호환성을 위해 계속 지원 되지만 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-172">Specifying the following elements as child elements of the `<identityConfiguration>` element has been deprecated, although the behavior is still supported for backward compatibility.</span></span> <span data-ttu-id="bc0d2-173">이러한 요소는 요소 아래에 지정 해야 합니다 [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="bc0d2-173">These elements should, instead, be specified under the [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) element.</span></span>
>
> - [\<audienceUris>](audienceuris.md)
> - [\<issuerNameRegistry>](issuernameregistry.md)
> - [\<issuerTokenResolver>](issuertokenresolver.md)
> - [\<serviceTokenResolver>](servicetokenresolver.md)

## <a name="example"></a><span data-ttu-id="bc0d2-174">예제</span><span class="sxs-lookup"><span data-stu-id="bc0d2-174">Example</span></span>

<span data-ttu-id="bc0d2-175">다음 예에서는 "alternateConfiguration" 라는 id 구성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-175">The following example creates an identity configuration named "alternateConfiguration".</span></span> <span data-ttu-id="bc0d2-176">Id 구성에서는 기본 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-176">The identity configuration specifies default settings.</span></span>

```xml
<system.identityModel>
    <identityConfiguration name="alternateConfiguration"/>
</system.identityModel>
```

## <a name="see-also"></a><span data-ttu-id="bc0d2-177">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bc0d2-177">See also</span></span>

- <xref:System.IdentityModel.Configuration.IdentityConfiguration>
- <xref:System.IdentityModel.Configuration.IdentityConfigurationElement>
