---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: e3e65820fa4dc341371d4f67689a288cd3f63951
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152569"
---
# <a name="securitytokenhandlerconfiguration"></a><span data-ttu-id="b44dd-101">\<보안토큰처리기구성></span><span class="sxs-lookup"><span data-stu-id="b44dd-101">\<securityTokenHandlerConfiguration></span></span>
<span data-ttu-id="b44dd-102">토큰 처리기 컬렉션에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b44dd-102">Provides configuration for the collection of token handlers.</span></span>  
  
<span data-ttu-id="b44dd-103">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b44dd-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b44dd-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="b44dd-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="b44dd-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<ID구성>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="b44dd-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="b44dd-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<보안토큰처리기>**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="b44dd-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="b44dd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<보안토큰처리기구성>**</span><span class="sxs-lookup"><span data-stu-id="b44dd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenHandlerConfiguration>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b44dd-108">구문</span><span class="sxs-lookup"><span data-stu-id="b44dd-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b44dd-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b44dd-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b44dd-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b44dd-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b44dd-111">특성</span><span class="sxs-lookup"><span data-stu-id="b44dd-111">Attributes</span></span>  
  
|<span data-ttu-id="b44dd-112">attribute</span><span class="sxs-lookup"><span data-stu-id="b44dd-112">Attribute</span></span>|<span data-ttu-id="b44dd-113">Description</span><span class="sxs-lookup"><span data-stu-id="b44dd-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b44dd-114">저장부트트랩컨텍스트</span><span class="sxs-lookup"><span data-stu-id="b44dd-114">saveBootstrapContext</span></span>|<span data-ttu-id="b44dd-115">부트스트랩 토큰을 세션 토큰에 포함할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b44dd-115">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="b44dd-116">idConfiguration>요소에 특성을 `saveBootstrapContext` 설정 하 여 토큰 처리기 컬렉션에 값을 설정할 수도 있습니다. [ \<](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="b44dd-116">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="b44dd-117">토큰 처리기 컬렉션에 설정된 값은 서비스에 설정된 값을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b44dd-117">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="b44dd-118">최대 클럭스큐</span><span class="sxs-lookup"><span data-stu-id="b44dd-118">maximumClockSkew</span></span>|<span data-ttu-id="b44dd-119">허용되는 <xref:System.TimeSpan> 최대 클럭 기울이기(기울이기)를 지정하는 A입니다.</span><span class="sxs-lookup"><span data-stu-id="b44dd-119">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="b44dd-120">로그인 세션이 만료 시간 유효성 검사와 같은 시간에 민감한 작업을 수행할 때 허용 되는 최대 클럭 오차를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="b44dd-120">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="b44dd-121">기본값은 5분 "00:05:00"입니다.</span><span class="sxs-lookup"><span data-stu-id="b44dd-121">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="b44dd-122">값을 지정하는 <xref:System.TimeSpan> 방법에 대한 자세한 내용은 [시간 범위 값을](../windows-workflow-foundation/index.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b44dd-122">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="b44dd-123">idConfiguration>요소에 특성을 `maximumClockSkew` 설정 하 여 최대 클럭 스큐를 서비스 수준에서 설정할 수도 있습니다. [ \<](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="b44dd-123">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="b44dd-124">토큰 처리기 컬렉션에 설정된 값은 서비스에 설정된 값을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b44dd-124">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b44dd-125">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b44dd-125">Child Elements</span></span>  
  
|<span data-ttu-id="b44dd-126">요소</span><span class="sxs-lookup"><span data-stu-id="b44dd-126">Element</span></span>|<span data-ttu-id="b44dd-127">Description</span><span class="sxs-lookup"><span data-stu-id="b44dd-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b44dd-128">\<청중우리></span><span class="sxs-lookup"><span data-stu-id="b44dd-128">\<audienceUris></span></span>](audienceuris.md)|<span data-ttu-id="b44dd-129">이 사용 당사자의 허용 가능한 식별자인 URI 집합을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b44dd-129">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="b44dd-130">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="b44dd-130">Optional.</span></span>|  
|[<span data-ttu-id="b44dd-131">\<캐시></span><span class="sxs-lookup"><span data-stu-id="b44dd-131">\<caches></span></span>](caches.md)|<span data-ttu-id="b44dd-132">세션 토큰 및 토큰 재생 검색에 사용되는 캐시를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="b44dd-132">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="b44dd-133">서비스 수준 또는 보안 토큰 처리기 컬렉션에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b44dd-133">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="b44dd-134">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="b44dd-134">Optional.</span></span>|  
|[<span data-ttu-id="b44dd-135">\<인증서 유효성 검사></span><span class="sxs-lookup"><span data-stu-id="b44dd-135">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="b44dd-136">토큰 처리기가 인증서의 유효성을 검사하는 데 사용하는 설정을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="b44dd-136">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="b44dd-137">서비스 수준 또는 보안 토큰 처리기 컬렉션에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b44dd-137">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="b44dd-138">특정 처리기가 자체 유효성 검사기로 구성된 경우 이러한 설정이 재정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="b44dd-138">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="b44dd-139">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="b44dd-139">Optional.</span></span>|  
|[<span data-ttu-id="b44dd-140">\<발급자이름레지스트리></span><span class="sxs-lookup"><span data-stu-id="b44dd-140">\<issuerNameRegistry></span></span>](issuernameregistry.md)|<span data-ttu-id="b44dd-141">토큰 처리기 컬렉션의 처리기에서 사용되는 발급자 이름 레지스트리를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b44dd-141">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="b44dd-142">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="b44dd-142">Optional.</span></span>|  
|[<span data-ttu-id="b44dd-143">\<발행자토큰해결러></span><span class="sxs-lookup"><span data-stu-id="b44dd-143">\<issuerTokenResolver></span></span>](issuertokenresolver.md)|<span data-ttu-id="b44dd-144">토큰 처리기 컬렉션의 처리기에서 사용되는 발급자 토큰 확인자를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="b44dd-144">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="b44dd-145">발급자 토큰 확인기는 들어오는 토큰 및 메시지에 서명 토큰을 해결하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b44dd-145">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="b44dd-146">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="b44dd-146">Optional.</span></span>|  
|[<span data-ttu-id="b44dd-147">\<서비스토큰 해결사></span><span class="sxs-lookup"><span data-stu-id="b44dd-147">\<serviceTokenResolver></span></span>](servicetokenresolver.md)|<span data-ttu-id="b44dd-148">토큰 처리기 컬렉션의 처리기에서 사용되는 서비스 토큰 확인자를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="b44dd-148">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="b44dd-149">서비스 토큰 확인기는 들어오는 토큰 및 메시지에서 암호화 토큰을 해결하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b44dd-149">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="b44dd-150">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="b44dd-150">Optional.</span></span>|  
|[<span data-ttu-id="b44dd-151">\<토큰 재생 감지></span><span class="sxs-lookup"><span data-stu-id="b44dd-151">\<tokenReplayDetection></span></span>](tokenreplaydetection.md)|<span data-ttu-id="b44dd-152">토큰 재생 검색을 활성화하고 토큰의 만료 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b44dd-152">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="b44dd-153">서비스 수준 또는 보안 토큰 처리기 컬렉션에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b44dd-153">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="b44dd-154">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="b44dd-154">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b44dd-155">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b44dd-155">Parent Elements</span></span>  
  
|<span data-ttu-id="b44dd-156">요소</span><span class="sxs-lookup"><span data-stu-id="b44dd-156">Element</span></span>|<span data-ttu-id="b44dd-157">Description</span><span class="sxs-lookup"><span data-stu-id="b44dd-157">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b44dd-158">\<보안토큰처리기></span><span class="sxs-lookup"><span data-stu-id="b44dd-158">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="b44dd-159">끝점에 등록된 보안 토큰 처리기 의 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b44dd-159">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b44dd-160">설명</span><span class="sxs-lookup"><span data-stu-id="b44dd-160">Remarks</span></span>  
 <span data-ttu-id="b44dd-161">이 섹션에서는 <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> 개체에 대한 속성 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b44dd-161">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="b44dd-162">이 섹션에서 구성된 설정은 서비스에 구성된 설정을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b44dd-162">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="b44dd-163">이러한 설정 중 일부는 처리기가 보안 토큰 처리기 컬렉션에 추가될 때 지정된 설정에 의해 재정의될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b44dd-163">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b44dd-164">예제</span><span class="sxs-lookup"><span data-stu-id="b44dd-164">Example</span></span>  
  
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
