---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: 330e52bd73a8032e4073fe434c852e5bdf8e1d47
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251881"
---
# <a name="securitytokenhandlerconfiguration"></a><span data-ttu-id="c65e2-101">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="c65e2-101">\<securityTokenHandlerConfiguration></span></span>
<span data-ttu-id="c65e2-102">토큰 처리기의 컬렉션에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c65e2-102">Provides configuration for the collection of token handlers.</span></span>  
  
<span data-ttu-id="c65e2-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c65e2-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c65e2-104">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="c65e2-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="c65e2-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="c65e2-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="c65e2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="c65e2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="c65e2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<securityTokenHandlerConfiguration >**</span><span class="sxs-lookup"><span data-stu-id="c65e2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenHandlerConfiguration>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c65e2-108">구문</span><span class="sxs-lookup"><span data-stu-id="c65e2-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c65e2-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c65e2-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c65e2-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c65e2-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c65e2-111">특성</span><span class="sxs-lookup"><span data-stu-id="c65e2-111">Attributes</span></span>  
  
|<span data-ttu-id="c65e2-112">특성</span><span class="sxs-lookup"><span data-stu-id="c65e2-112">Attribute</span></span>|<span data-ttu-id="c65e2-113">Description</span><span class="sxs-lookup"><span data-stu-id="c65e2-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c65e2-114">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="c65e2-114">saveBootstrapContext</span></span>|<span data-ttu-id="c65e2-115">부트스트랩 토큰이 세션 토큰에 포함 되어야 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c65e2-115">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="c65e2-116">`saveBootstrapContext` [IdentityConfiguration > 요소에 대 한 특성을 설정 하 여 토큰 처리기 컬렉션에서 값을 설정할 수도 있습니다. \<](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="c65e2-116">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="c65e2-117">토큰 처리기 컬렉션에 설정 된 값은 서비스에 설정 된 값을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c65e2-117">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="c65e2-118">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="c65e2-118">maximumClockSkew</span></span>|<span data-ttu-id="c65e2-119">허용 되는 최대 클록 오차를 지정 하는입니다.<xref:System.TimeSpan></span><span class="sxs-lookup"><span data-stu-id="c65e2-119">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="c65e2-120">로그인 세션이 만료 시간 유효성 검사와 같은 시간에 민감한 작업을 수행할 때 허용 되는 최대 클럭 오차를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="c65e2-120">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="c65e2-121">기본값은 5 분 "00:05:00"입니다.</span><span class="sxs-lookup"><span data-stu-id="c65e2-121">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="c65e2-122">값을 지정 <xref:System.TimeSpan> 하는 방법에 대 한 자세한 내용은 [Timespan 값](../windows-workflow-foundation/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c65e2-122">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="c65e2-123">IdentityConfiguration > 요소 `maximumClockSkew` 에 특성을 설정 하 여 서비스 수준에서 최대 클럭 오차를 설정할 수도 있습니다. [ \<](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="c65e2-123">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="c65e2-124">토큰 처리기 컬렉션에 설정 된 값은 서비스에 설정 된 값을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c65e2-124">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c65e2-125">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c65e2-125">Child Elements</span></span>  
  
|<span data-ttu-id="c65e2-126">요소</span><span class="sxs-lookup"><span data-stu-id="c65e2-126">Element</span></span>|<span data-ttu-id="c65e2-127">Description</span><span class="sxs-lookup"><span data-stu-id="c65e2-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c65e2-128">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="c65e2-128">\<audienceUris></span></span>](audienceuris.md)|<span data-ttu-id="c65e2-129">이 신뢰 당사자의 허용 되는 식별자에 해당 하는 Uri 집합을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c65e2-129">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="c65e2-130">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c65e2-130">Optional.</span></span>|  
|[<span data-ttu-id="c65e2-131">\<caches></span><span class="sxs-lookup"><span data-stu-id="c65e2-131">\<caches></span></span>](caches.md)|<span data-ttu-id="c65e2-132">세션 토큰 및 토큰 재생 검색에 사용 되는 캐시를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c65e2-132">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="c65e2-133">는 서비스 수준 또는 보안 토큰 처리기 컬렉션에서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c65e2-133">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="c65e2-134">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c65e2-134">Optional.</span></span>|  
|[<span data-ttu-id="c65e2-135">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="c65e2-135">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="c65e2-136">토큰 처리기에서 인증서의 유효성을 검사 하는 데 사용 하는 설정을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="c65e2-136">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="c65e2-137">는 서비스 수준 또는 보안 토큰 처리기 컬렉션에서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c65e2-137">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="c65e2-138">이러한 설정은 고유한 유효성 검사기를 사용 하 여 특정 처리기를 구성 하는 경우 재정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c65e2-138">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="c65e2-139">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c65e2-139">Optional.</span></span>|  
|[<span data-ttu-id="c65e2-140">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="c65e2-140">\<issuerNameRegistry></span></span>](issuernameregistry.md)|<span data-ttu-id="c65e2-141">토큰 처리기 컬렉션의 처리기에서 사용 하는 발급자 이름 레지스트리를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c65e2-141">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="c65e2-142">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c65e2-142">Optional.</span></span>|  
|[<span data-ttu-id="c65e2-143">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="c65e2-143">\<issuerTokenResolver></span></span>](issuertokenresolver.md)|<span data-ttu-id="c65e2-144">토큰 처리기 컬렉션의 처리기에서 사용 하는 발급자 토큰 확인자를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c65e2-144">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="c65e2-145">발급자 토큰 확인자는 들어오는 토큰과 메시지의 서명 토큰을 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c65e2-145">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="c65e2-146">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c65e2-146">Optional.</span></span>|  
|[<span data-ttu-id="c65e2-147">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="c65e2-147">\<serviceTokenResolver></span></span>](servicetokenresolver.md)|<span data-ttu-id="c65e2-148">토큰 처리기 컬렉션의 처리기에서 사용 하는 서비스 토큰 확인자를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c65e2-148">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="c65e2-149">서비스 토큰 확인자는 들어오는 토큰과 메시지의 암호화 토큰을 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c65e2-149">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="c65e2-150">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c65e2-150">Optional.</span></span>|  
|[<span data-ttu-id="c65e2-151">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="c65e2-151">\<tokenReplayDetection></span></span>](tokenreplaydetection.md)|<span data-ttu-id="c65e2-152">토큰 재생 검색을 사용 하도록 설정 하 고 토큰의 만료 시간을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c65e2-152">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="c65e2-153">는 서비스 수준 또는 보안 토큰 처리기 컬렉션에서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c65e2-153">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="c65e2-154">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c65e2-154">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c65e2-155">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c65e2-155">Parent Elements</span></span>  
  
|<span data-ttu-id="c65e2-156">요소</span><span class="sxs-lookup"><span data-stu-id="c65e2-156">Element</span></span>|<span data-ttu-id="c65e2-157">Description</span><span class="sxs-lookup"><span data-stu-id="c65e2-157">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c65e2-158">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="c65e2-158">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="c65e2-159">끝점에 등록 된 보안 토큰 처리기의 컬렉션을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c65e2-159">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c65e2-160">설명</span><span class="sxs-lookup"><span data-stu-id="c65e2-160">Remarks</span></span>  
 <span data-ttu-id="c65e2-161">이 섹션에서는 <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> 개체의 속성 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c65e2-161">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="c65e2-162">이 섹션에서 구성 된 설정은 서비스에 구성 된 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c65e2-162">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="c65e2-163">이러한 설정 중 일부는 보안 토큰 처리기 컬렉션에 처리기를 추가할 때 지정 된 설정에 의해 재정의 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c65e2-163">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c65e2-164">예제</span><span class="sxs-lookup"><span data-stu-id="c65e2-164">Example</span></span>  
  
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
