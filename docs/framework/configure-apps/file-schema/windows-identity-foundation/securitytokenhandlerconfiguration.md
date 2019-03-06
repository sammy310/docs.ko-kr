---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: 29e18cdda9e18addef4f0f32fd30e9abf6af78fc
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57360409"
---
# <a name="securitytokenhandlerconfiguration"></a><span data-ttu-id="b02e5-101">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="b02e5-101">\<securityTokenHandlerConfiguration></span></span>
<span data-ttu-id="b02e5-102">토큰 처리기 컬렉션에 대 한 구성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b02e5-102">Provides configuration for the collection of token handlers.</span></span>  
  
 <span data-ttu-id="b02e5-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="b02e5-103">\<system.identityModel></span></span>  
<span data-ttu-id="b02e5-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="b02e5-104">\<identityConfiguration></span></span>  
<span data-ttu-id="b02e5-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="b02e5-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="b02e5-106">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="b02e5-106">\<securityTokenHandlerConfiguration></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b02e5-107">구문</span><span class="sxs-lookup"><span data-stu-id="b02e5-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration saveBootstrapContext=xs:boolean  
          maximumClockSkew=TimeSpan>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b02e5-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b02e5-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b02e5-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b02e5-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b02e5-110">특성</span><span class="sxs-lookup"><span data-stu-id="b02e5-110">Attributes</span></span>  
  
|<span data-ttu-id="b02e5-111">특성</span><span class="sxs-lookup"><span data-stu-id="b02e5-111">Attribute</span></span>|<span data-ttu-id="b02e5-112">설명</span><span class="sxs-lookup"><span data-stu-id="b02e5-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b02e5-113">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="b02e5-113">saveBootstrapContext</span></span>|<span data-ttu-id="b02e5-114">세션 토큰에 부트스트랩 토큰을 포함시킬지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b02e5-114">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="b02e5-115">값을 설정할 수도 있습니다 토큰 처리기 컬렉션에 대해 설정 하 여 합니다 `saveBootstrapContext` 특성을 [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b02e5-115">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="b02e5-116">토큰 처리기 컬렉션에 대해 설정 된 값에는 서비스에서 설정한 값 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="b02e5-116">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="b02e5-117">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="b02e5-117">maximumClockSkew</span></span>|<span data-ttu-id="b02e5-118"><xref:System.TimeSpan> 허용 된 최대 클럭 오차를 지정 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="b02e5-118">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="b02e5-119">로그인 세션이 만료 시간 유효성 검사와 같은 시간에 민감한 작업을 수행할 때 허용 되는 최대 클럭 오차를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="b02e5-119">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="b02e5-120">기본값은 5 분 "00: 05:00"입니다.</span><span class="sxs-lookup"><span data-stu-id="b02e5-120">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="b02e5-121">지정 하는 방법에 대 한 자세한 내용은 <xref:System.TimeSpan> 값을 참조 하세요 [Timespan 값](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b02e5-121">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="b02e5-122">최대 클럭 오차 설정할 수도 있습니다 서비스 수준에서 설정 하 여 합니다 `maximumClockSkew` 특성을 [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b02e5-122">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="b02e5-123">토큰 처리기 컬렉션에 대해 설정 된 값에는 서비스에서 설정한 값 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="b02e5-123">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b02e5-124">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b02e5-124">Child Elements</span></span>  
  
|<span data-ttu-id="b02e5-125">요소</span><span class="sxs-lookup"><span data-stu-id="b02e5-125">Element</span></span>|<span data-ttu-id="b02e5-126">설명</span><span class="sxs-lookup"><span data-stu-id="b02e5-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b02e5-127">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="b02e5-127">\<audienceUris></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)|<span data-ttu-id="b02e5-128">이 신뢰 당사자의 식별자를 허용 되는 Uri 집합을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b02e5-128">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="b02e5-129">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b02e5-129">Optional.</span></span>|  
|[<span data-ttu-id="b02e5-130">\<caches></span><span class="sxs-lookup"><span data-stu-id="b02e5-130">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="b02e5-131">세션 토큰 및 토큰 재생 검색에 사용 되는 캐시를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b02e5-131">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="b02e5-132">서비스 수준 또는 보안 토큰 처리기 컬렉션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b02e5-132">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="b02e5-133">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b02e5-133">Optional.</span></span>|  
|[<span data-ttu-id="b02e5-134">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="b02e5-134">\<certificateValidation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|<span data-ttu-id="b02e5-135">토큰 처리기 인증서의 유효성을 검사 하는 데 사용 되는 설정을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="b02e5-135">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="b02e5-136">서비스 수준 또는 보안 토큰 처리기 컬렉션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b02e5-136">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="b02e5-137">특정 처리기를 자체 유효성 검사기를 사용 하 여 구성 된 경우이 설정은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b02e5-137">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="b02e5-138">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b02e5-138">Optional.</span></span>|  
|[<span data-ttu-id="b02e5-139">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="b02e5-139">\<issuerNameRegistry></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|<span data-ttu-id="b02e5-140">토큰 처리기 컬렉션의 처리기에서 사용 되는 발급자 이름 레지스트리를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b02e5-140">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="b02e5-141">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b02e5-141">Optional.</span></span>|  
|[<span data-ttu-id="b02e5-142">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="b02e5-142">\<issuerTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)|<span data-ttu-id="b02e5-143">토큰 처리기 컬렉션의 처리기에서 사용 되는 발급자 토큰 확인자를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b02e5-143">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="b02e5-144">발급자 토큰 확인자는 들어오는 토큰 및 메시지에 서명 토큰을 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b02e5-144">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="b02e5-145">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b02e5-145">Optional.</span></span>|  
|[<span data-ttu-id="b02e5-146">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="b02e5-146">\<serviceTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)|<span data-ttu-id="b02e5-147">토큰 처리기 컬렉션의 처리기에서 사용 되는 서비스 토큰 확인자를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b02e5-147">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="b02e5-148">서비스 토큰 확인자는 들어오는 토큰에 메시지 암호화 토큰을 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b02e5-148">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="b02e5-149">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b02e5-149">Optional.</span></span>|  
|[<span data-ttu-id="b02e5-150">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="b02e5-150">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|<span data-ttu-id="b02e5-151">토큰 재생 검색을 사용 하도록 설정 하 고 토큰에 대 한 만료 시간을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b02e5-151">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="b02e5-152">서비스 수준 또는 보안 토큰 처리기 컬렉션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b02e5-152">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="b02e5-153">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b02e5-153">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b02e5-154">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b02e5-154">Parent Elements</span></span>  
  
|<span data-ttu-id="b02e5-155">요소</span><span class="sxs-lookup"><span data-stu-id="b02e5-155">Element</span></span>|<span data-ttu-id="b02e5-156">설명</span><span class="sxs-lookup"><span data-stu-id="b02e5-156">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b02e5-157">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="b02e5-157">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="b02e5-158">끝점을 사용 하 여 등록 된 보안 토큰 처리기 컬렉션을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b02e5-158">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b02e5-159">설명</span><span class="sxs-lookup"><span data-stu-id="b02e5-159">Remarks</span></span>  
 <span data-ttu-id="b02e5-160">이 섹션에서는 속성 값을 <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="b02e5-160">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="b02e5-161">이 섹션에 구성 된 설정 서비스에서 구성한 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b02e5-161">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="b02e5-162">이러한 설정 중 일부 처리기는 보안 토큰 처리기 컬렉션에 추가 되 면 지정 된 설정으로 재정의 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b02e5-162">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b02e5-163">예제</span><span class="sxs-lookup"><span data-stu-id="b02e5-163">Example</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>   
      <securityTokenHandlerConfiguration>  
  
        <audienceUris>  
          <clear/>  
          <add value="http://www.example.com/myapp/" />  
        </audienceUris>  
  
        <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel">  
          <trustedIssuers>  
            <add thumbprint="97249e1a … 4c9158de" name="contoso.com" />  
          </trustedIssuers>  
        </issuerNameRegistry>  
  
        <issuerTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
  
        <serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```
