---
title: <identityConfiguration>
ms.date: 03/30/2017
ms.assetid: 1db76253-07da-447b-9e7a-3705c7228cf4
author: BrucePerlerMS
ms.openlocfilehash: 0fa8c574fd5663606cf081f1000a24884306edfe
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251991"
---
# \<identityConfiguration>

<span data-ttu-id="c6b55-101">서비스 수준 id 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-101">Specifies service-level identity settings.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<identityConfiguration>**  

## <a name="syntax"></a><span data-ttu-id="c6b55-102">구문</span><span class="sxs-lookup"><span data-stu-id="c6b55-102">Syntax</span></span>

```xml
<system.identityModel>
  <identityConfiguration
      name=xs:string
      saveBootstrapContext=xs:boolean>
      maximumClockSkew=TimeSpan >
  </identityConfiguration>
</system.identityModel>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c6b55-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c6b55-103">Attributes and Elements</span></span>

<span data-ttu-id="c6b55-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-104">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="c6b55-105">특성</span><span class="sxs-lookup"><span data-stu-id="c6b55-105">Attributes</span></span>

|<span data-ttu-id="c6b55-106">attribute</span><span class="sxs-lookup"><span data-stu-id="c6b55-106">Attribute</span></span>|<span data-ttu-id="c6b55-107">Description</span><span class="sxs-lookup"><span data-stu-id="c6b55-107">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="c6b55-108">name</span><span class="sxs-lookup"><span data-stu-id="c6b55-108">name</span></span>|<span data-ttu-id="c6b55-109">Id 구성 섹션의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-109">The name of the identity configuration section.</span></span> <span data-ttu-id="c6b55-110">이 이름을 사용 하 여 특정 구성 섹션을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-110">You can use this name to reference a specific configuration section.</span></span> <span data-ttu-id="c6b55-111">특성을 `name` 지정 하지 않으면 섹션에서 기본 구성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-111">If no `name` attribute is specified, the section defines the default configuration.</span></span> <span data-ttu-id="c6b55-112">기본 구성은 항상 수동 페더레이션 시나리오에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-112">The default configuration is always used for passive federation scenarios.</span></span> <span data-ttu-id="c6b55-113">자세한 내용은 요소를 참조 하세요 [\<federationConfiguration>](federationconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="c6b55-113">For more information, see the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>|
|<span data-ttu-id="c6b55-114">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="c6b55-114">saveBootstrapContext</span></span>|<span data-ttu-id="c6b55-115">부트스트랩 토큰이 세션 토큰에 포함 되어야 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-115">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="c6b55-116">`saveBootstrapContext`요소에 대 한 특성을 설정 하 여 토큰 처리기 컬렉션에서 값을 설정할 수도 있습니다 [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="c6b55-116">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) element.</span></span> <span data-ttu-id="c6b55-117">토큰 처리기 컬렉션에 설정 된 값은 서비스에 설정 된 값을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-117">A value set on the token handler collection overrides the value set on the service.</span></span>|
|<span data-ttu-id="c6b55-118">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="c6b55-118">maximumClockSkew</span></span>|<span data-ttu-id="c6b55-119"><xref:System.TimeSpan>허용 되는 최대 클록 오차를 지정 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-119">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="c6b55-120">로그인 세션이 만료 시간 유효성 검사와 같은 시간에 민감한 작업을 수행할 때 허용 되는 최대 클럭 오차를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-120">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="c6b55-121">기본값은 5 분 "00:05:00"입니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-121">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="c6b55-122">값을 지정 하는 방법에 대 한 자세한 내용은 <xref:System.TimeSpan> [Timespan 값](../windows-workflow-foundation/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c6b55-122">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="c6b55-123">`maximumClockSkew`요소에 대 한 특성을 설정 하 여 토큰 처리기 컬렉션에서 최대 클록 오차를 설정할 수도 있습니다 [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="c6b55-123">The maximum clock skew may also be set on a token handler collection by setting the `maximumClockSkew` attribute on the [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) element.</span></span> <span data-ttu-id="c6b55-124">토큰 처리기 컬렉션에 설정 된 값은 서비스에 설정 된 값을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-124">A value set on the token handler collection overrides the value set on the service.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="c6b55-125">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c6b55-125">Child Elements</span></span>

|<span data-ttu-id="c6b55-126">요소</span><span class="sxs-lookup"><span data-stu-id="c6b55-126">Element</span></span>|<span data-ttu-id="c6b55-127">Description</span><span class="sxs-lookup"><span data-stu-id="c6b55-127">Description</span></span>|
|-------------|-----------------|
|[\<caches>](caches.md)|<span data-ttu-id="c6b55-128">세션 토큰 및 토큰 재생 검색에 사용 되는 캐시를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-128">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="c6b55-129">는 서비스 수준 또는 보안 토큰 처리기 컬렉션에서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-129">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="c6b55-130">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-130">Optional.</span></span>|
|[\<certificateValidation>](certificatevalidation.md)|<span data-ttu-id="c6b55-131">토큰 처리기에서 인증서의 유효성을 검사 하는 데 사용 하는 설정을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-131">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="c6b55-132">는 서비스 수준 또는 보안 토큰 처리기 컬렉션에서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-132">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="c6b55-133">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-133">Optional.</span></span>|
|[\<claimsAuthenticationManager>](claimsauthenticationmanager.md)|<span data-ttu-id="c6b55-134">들어오는 클레임에 대 한 클레임 인증 관리자를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-134">Registers a claims authentication manager for the incoming claims.</span></span> <span data-ttu-id="c6b55-135">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-135">Optional.</span></span>|
|[\<claimsAuthorizationManager>](claimsauthorizationmanager.md)|<span data-ttu-id="c6b55-136">들어오는 클레임에 대 한 클레임 권한 부여 관리자를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-136">Registers a claims authorization manager for the incoming claims.</span></span> <span data-ttu-id="c6b55-137">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-137">Optional.</span></span>|
|[\<claimTypeRequired>](claimtyperequired.md)|<span data-ttu-id="c6b55-138">들어오는 보안 토큰에 대 한 필수 클레임 집합을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-138">Specifies the set of required claims for incoming security tokens.</span></span> <span data-ttu-id="c6b55-139">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-139">Optional.</span></span>|
|[\<securityTokenHandlers>](securitytokenhandlers.md)|<span data-ttu-id="c6b55-140">보안 토큰 처리기의 컬렉션을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-140">Specifies a collection of security token handlers.</span></span> <span data-ttu-id="c6b55-141">0 개 이상의 보안 토큰 처리기 컬렉션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-141">Zero or more collections of security token handlers can be specified.</span></span> <span data-ttu-id="c6b55-142">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-142">Optional.</span></span>|
|[\<tokenReplayDetection>](tokenreplaydetection.md)|<span data-ttu-id="c6b55-143">토큰 재생 검색을 사용 하도록 설정 하 고 토큰의 만료 시간을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-143">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="c6b55-144">는 서비스 수준 또는 보안 토큰 처리기 컬렉션에서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-144">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="c6b55-145">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-145">Optional.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="c6b55-146">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c6b55-146">Parent Elements</span></span>

|<span data-ttu-id="c6b55-147">요소</span><span class="sxs-lookup"><span data-stu-id="c6b55-147">Element</span></span>|<span data-ttu-id="c6b55-148">Description</span><span class="sxs-lookup"><span data-stu-id="c6b55-148">Description</span></span>|
|-------------|-----------------|
|[\<system.identityModel>](system-identitymodel.md)|<span data-ttu-id="c6b55-149">응용 프로그램에서 WIF (Windows Identity Foundation) 옵션을 사용 하도록 구성 하는 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-149">Provides configuration for enabling Windows Identity Foundation (WIF) options in applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c6b55-150">설명</span><span class="sxs-lookup"><span data-stu-id="c6b55-150">Remarks</span></span>

<span data-ttu-id="c6b55-151">각각 고유한 이름을 가진 여러 id 구성이 정의 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-151">Multiple identity configurations may be defined, each with a unique name.</span></span> <span data-ttu-id="c6b55-152">동작은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-152">The behavior is as follows:</span></span>

1. <span data-ttu-id="c6b55-153">요소가 지정 되지 않은 경우 `<identityConfiguration>` 입니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-153">If no `<identityConfiguration>` element is specified.</span></span> <span data-ttu-id="c6b55-154">기본 id 구성은 런타임에 만들어지며 기본값으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-154">A default identity configuration is created at runtime and populated with default values.</span></span>

2. <span data-ttu-id="c6b55-155">단일 `<identityConfiguration>` 요소가 지정 된 경우</span><span class="sxs-lookup"><span data-stu-id="c6b55-155">If a single `<identityConfiguration>` element is specified.</span></span> <span data-ttu-id="c6b55-156">기본 id 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-156">It is the default identity configuration.</span></span> <span data-ttu-id="c6b55-157">이름이 지정 되거나 이름이 지정 되지 않은 경우에는 중요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-157">It does not matter whether it is named or unnamed.</span></span>

3. <span data-ttu-id="c6b55-158">여러 `<identityConfiguration>` 요소가 지정 된 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-158">If multiple `<identityConfiguration>` elements are specified.</span></span> <span data-ttu-id="c6b55-159">명명 되지 않은 요소는 기본 id 구성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-159">The unnamed element specifies the default identity configuration.</span></span> <span data-ttu-id="c6b55-160">여러 요소를 지정 하는 경우 `<identityConfiguration>` 둘 중 하나를 명명 되지 않은 상태로 지정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-160">It is recommended that when you specify multiple `<identityConfiguration>` elements, one of them should be unnamed.</span></span>

> [!WARNING]
> <span data-ttu-id="c6b55-161">여러 요소를 지정 하는 경우 그 중 하나에 이름이 지정 되지 `<identityConfiguration>` 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-161">If you specify multiple `<identityConfiguration>` elements, one of them should be unnamed.</span></span> <span data-ttu-id="c6b55-162">명명 되지 않은 요소는 기본 id 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-162">The unnamed element will be the default identity configuration.</span></span>

 <span data-ttu-id="c6b55-163">요소에 지정 된 설정 중 일부는 `<identityConfiguration>` 보안 토큰 처리기 컬렉션의 설정 또는 개별 보안 토큰 처리기의 설정에 의해 재정의 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-163">Some of the settings specified in the `<identityConfiguration>` element can be overridden by settings on a security token handler collection or by settings on individual security token handlers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c6b55-164">또는 클래스를 사용 하 여 <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> 코드에서 클레임 기반 액세스 제어를 제공 하는 경우 요소에서 참조 하는 id 구성은 `<federationConfiguration>` 권한 부여 관리자와 권한 부여 결정을 내리는 데 사용 되는 정책을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-164">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the identity configuration that is referenced by the `<federationConfiguration>` element configures the claims authorization manager and policy that is used to make authorization decisions.</span></span> <span data-ttu-id="c6b55-165">이는 Windows Communication Foundation (WCF) 응용 프로그램 또는 웹 기반이 아닌 응용 프로그램 등 수동 웹 시나리오가 아닌 시나리오 에서도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-165">This is true, even in scenarios that are not passive Web scenarios, for example Windows Communication Foundation (WCF) applications or an application that is not Web-based.</span></span> <span data-ttu-id="c6b55-166">응용 프로그램이 수동 웹 응용 프로그램이 아닌 경우 참조 되는 [\<claimsAuthorizationManager>](claimsauthorizationmanager.md) id 구성의 요소 및 자식 정책 요소 (있는 경우)만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-166">If the application is not a passive Web application, the [\<claimsAuthorizationManager>](claimsauthorizationmanager.md) element (and its child policy elements, if present) of the referenced identity configuration are the only settings applied.</span></span> <span data-ttu-id="c6b55-167">다른 모든 설정은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-167">All other settings are ignored.</span></span> <span data-ttu-id="c6b55-168">자세한 내용은 요소를 참조 하세요 [\<federationConfiguration>](federationconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="c6b55-168">For more information, see the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>

<span data-ttu-id="c6b55-169">합니다 `<identityConfiguration>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Configuration.IdentityConfigurationElement> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-169">The `<identityConfiguration>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityConfigurationElement> class.</span></span> <span data-ttu-id="c6b55-170">Id 구성 섹션은 클래스로 표현 됩니다 <xref:System.IdentityModel.Configuration.IdentityConfiguration> .</span><span class="sxs-lookup"><span data-stu-id="c6b55-170">An identity configuration section is represented by the <xref:System.IdentityModel.Configuration.IdentityConfiguration> class.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c6b55-171">다음 요소를 요소의 자식 요소로 지정 하는 기능은 `<identityConfiguration>` 이전 버전과의 호환성을 위해 계속 지원 되지만 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-171">Specifying the following elements as child elements of the `<identityConfiguration>` element has been deprecated, although the behavior is still supported for backward compatibility.</span></span> <span data-ttu-id="c6b55-172">이러한 요소는 요소 아래에 지정 해야 합니다 [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="c6b55-172">These elements should, instead, be specified under the [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) element.</span></span>
>
> - [\<audienceUris>](audienceuris.md)
> - [\<issuerNameRegistry>](issuernameregistry.md)
> - [\<issuerTokenResolver>](issuertokenresolver.md)
> - [\<serviceTokenResolver>](servicetokenresolver.md)

## <a name="example"></a><span data-ttu-id="c6b55-173">예제</span><span class="sxs-lookup"><span data-stu-id="c6b55-173">Example</span></span>

<span data-ttu-id="c6b55-174">다음 예에서는 "alternateConfiguration" 라는 id 구성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-174">The following example creates an identity configuration named "alternateConfiguration".</span></span> <span data-ttu-id="c6b55-175">Id 구성에서는 기본 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6b55-175">The identity configuration specifies default settings.</span></span>

```xml
<system.identityModel>
    <identityConfiguration name="alternateConfiguration"/>
</system.identityModel>
```

## <a name="see-also"></a><span data-ttu-id="c6b55-176">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c6b55-176">See also</span></span>

- <xref:System.IdentityModel.Configuration.IdentityConfiguration>
- <xref:System.IdentityModel.Configuration.IdentityConfigurationElement>
