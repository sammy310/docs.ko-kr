---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: 0aefaa808dfc32085a208420fcd582b1671acc64
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942449"
---
# <a name="securitytokenhandlerconfiguration"></a><span data-ttu-id="ae92c-101">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="ae92c-101">\<securityTokenHandlerConfiguration></span></span>
<span data-ttu-id="ae92c-102">토큰 처리기의 컬렉션에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae92c-102">Provides configuration for the collection of token handlers.</span></span>  
  
 <span data-ttu-id="ae92c-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="ae92c-103">\<system.identityModel></span></span>  
<span data-ttu-id="ae92c-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="ae92c-104">\<identityConfiguration></span></span>  
<span data-ttu-id="ae92c-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="ae92c-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="ae92c-106">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="ae92c-106">\<securityTokenHandlerConfiguration></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae92c-107">구문</span><span class="sxs-lookup"><span data-stu-id="ae92c-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ae92c-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ae92c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ae92c-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ae92c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ae92c-110">특성</span><span class="sxs-lookup"><span data-stu-id="ae92c-110">Attributes</span></span>  
  
|<span data-ttu-id="ae92c-111">특성</span><span class="sxs-lookup"><span data-stu-id="ae92c-111">Attribute</span></span>|<span data-ttu-id="ae92c-112">설명</span><span class="sxs-lookup"><span data-stu-id="ae92c-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ae92c-113">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="ae92c-113">saveBootstrapContext</span></span>|<span data-ttu-id="ae92c-114">부트스트랩 토큰이 세션 토큰에 포함 되어야 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae92c-114">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="ae92c-115">`saveBootstrapContext` [IdentityConfiguration > 요소에 대 한 특성을 설정 하 여 토큰 처리기 컬렉션에서 값을 설정할 수도 있습니다. \<](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="ae92c-115">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="ae92c-116">토큰 처리기 컬렉션에 설정 된 값은 서비스에 설정 된 값을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae92c-116">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="ae92c-117">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="ae92c-117">maximumClockSkew</span></span>|<span data-ttu-id="ae92c-118">허용 되는 최대 클록 오차를 지정 하는입니다.<xref:System.TimeSpan></span><span class="sxs-lookup"><span data-stu-id="ae92c-118">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="ae92c-119">로그인 세션이 만료 시간 유효성 검사와 같은 시간에 민감한 작업을 수행할 때 허용 되는 최대 클럭 오차를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae92c-119">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="ae92c-120">기본값은 5 분 "00:05:00"입니다.</span><span class="sxs-lookup"><span data-stu-id="ae92c-120">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="ae92c-121">값을 지정 <xref:System.TimeSpan> 하는 방법에 대 한 자세한 내용은 [Timespan 값](../windows-workflow-foundation/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ae92c-121">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="ae92c-122">IdentityConfiguration > 요소 `maximumClockSkew` 에 특성을 설정 하 여 서비스 수준에서 최대 클럭 오차를 설정할 수도 있습니다. [ \<](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="ae92c-122">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="ae92c-123">토큰 처리기 컬렉션에 설정 된 값은 서비스에 설정 된 값을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae92c-123">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ae92c-124">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ae92c-124">Child Elements</span></span>  
  
|<span data-ttu-id="ae92c-125">요소</span><span class="sxs-lookup"><span data-stu-id="ae92c-125">Element</span></span>|<span data-ttu-id="ae92c-126">설명</span><span class="sxs-lookup"><span data-stu-id="ae92c-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ae92c-127">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="ae92c-127">\<audienceUris></span></span>](audienceuris.md)|<span data-ttu-id="ae92c-128">이 신뢰 당사자의 허용 되는 식별자에 해당 하는 Uri 집합을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae92c-128">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="ae92c-129">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="ae92c-129">Optional.</span></span>|  
|[<span data-ttu-id="ae92c-130">\<caches></span><span class="sxs-lookup"><span data-stu-id="ae92c-130">\<caches></span></span>](caches.md)|<span data-ttu-id="ae92c-131">세션 토큰 및 토큰 재생 검색에 사용 되는 캐시를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae92c-131">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="ae92c-132">는 서비스 수준 또는 보안 토큰 처리기 컬렉션에서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae92c-132">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="ae92c-133">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="ae92c-133">Optional.</span></span>|  
|[<span data-ttu-id="ae92c-134">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="ae92c-134">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="ae92c-135">토큰 처리기에서 인증서의 유효성을 검사 하는 데 사용 하는 설정을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae92c-135">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="ae92c-136">는 서비스 수준 또는 보안 토큰 처리기 컬렉션에서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae92c-136">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="ae92c-137">이러한 설정은 고유한 유효성 검사기를 사용 하 여 특정 처리기를 구성 하는 경우 재정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae92c-137">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="ae92c-138">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="ae92c-138">Optional.</span></span>|  
|[<span data-ttu-id="ae92c-139">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="ae92c-139">\<issuerNameRegistry></span></span>](issuernameregistry.md)|<span data-ttu-id="ae92c-140">토큰 처리기 컬렉션의 처리기에서 사용 하는 발급자 이름 레지스트리를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae92c-140">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="ae92c-141">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="ae92c-141">Optional.</span></span>|  
|[<span data-ttu-id="ae92c-142">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="ae92c-142">\<issuerTokenResolver></span></span>](issuertokenresolver.md)|<span data-ttu-id="ae92c-143">토큰 처리기 컬렉션의 처리기에서 사용 하는 발급자 토큰 확인자를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae92c-143">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="ae92c-144">발급자 토큰 확인자는 들어오는 토큰과 메시지의 서명 토큰을 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae92c-144">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="ae92c-145">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="ae92c-145">Optional.</span></span>|  
|[<span data-ttu-id="ae92c-146">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="ae92c-146">\<serviceTokenResolver></span></span>](servicetokenresolver.md)|<span data-ttu-id="ae92c-147">토큰 처리기 컬렉션의 처리기에서 사용 하는 서비스 토큰 확인자를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae92c-147">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="ae92c-148">서비스 토큰 확인자는 들어오는 토큰과 메시지의 암호화 토큰을 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae92c-148">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="ae92c-149">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="ae92c-149">Optional.</span></span>|  
|[<span data-ttu-id="ae92c-150">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="ae92c-150">\<tokenReplayDetection></span></span>](tokenreplaydetection.md)|<span data-ttu-id="ae92c-151">토큰 재생 검색을 사용 하도록 설정 하 고 토큰의 만료 시간을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae92c-151">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="ae92c-152">는 서비스 수준 또는 보안 토큰 처리기 컬렉션에서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae92c-152">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="ae92c-153">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="ae92c-153">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ae92c-154">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ae92c-154">Parent Elements</span></span>  
  
|<span data-ttu-id="ae92c-155">요소</span><span class="sxs-lookup"><span data-stu-id="ae92c-155">Element</span></span>|<span data-ttu-id="ae92c-156">Description</span><span class="sxs-lookup"><span data-stu-id="ae92c-156">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ae92c-157">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="ae92c-157">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="ae92c-158">끝점에 등록 된 보안 토큰 처리기의 컬렉션을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae92c-158">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae92c-159">설명</span><span class="sxs-lookup"><span data-stu-id="ae92c-159">Remarks</span></span>  
 <span data-ttu-id="ae92c-160">이 섹션에서는 <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> 개체의 속성 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae92c-160">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="ae92c-161">이 섹션에서 구성 된 설정은 서비스에 구성 된 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae92c-161">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="ae92c-162">이러한 설정 중 일부는 보안 토큰 처리기 컬렉션에 처리기를 추가할 때 지정 된 설정에 의해 재정의 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae92c-162">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae92c-163">예제</span><span class="sxs-lookup"><span data-stu-id="ae92c-163">Example</span></span>  
  
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
