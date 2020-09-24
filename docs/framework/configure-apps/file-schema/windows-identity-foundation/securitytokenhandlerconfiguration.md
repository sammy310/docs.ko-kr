---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: 4c6affbc24a58424158e466fb732e9a3b3d6f1ed
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157020"
---
# \<securityTokenHandlerConfiguration>

<span data-ttu-id="aec0e-101">토큰 처리기의 컬렉션에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="aec0e-101">Provides configuration for the collection of token handlers.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenHandlerConfiguration>**  
  
## <a name="syntax"></a><span data-ttu-id="aec0e-102">구문</span><span class="sxs-lookup"><span data-stu-id="aec0e-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aec0e-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="aec0e-103">Attributes and Elements</span></span>  

 <span data-ttu-id="aec0e-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="aec0e-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aec0e-105">특성</span><span class="sxs-lookup"><span data-stu-id="aec0e-105">Attributes</span></span>  
  
|<span data-ttu-id="aec0e-106">attribute</span><span class="sxs-lookup"><span data-stu-id="aec0e-106">Attribute</span></span>|<span data-ttu-id="aec0e-107">설명</span><span class="sxs-lookup"><span data-stu-id="aec0e-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aec0e-108">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="aec0e-108">saveBootstrapContext</span></span>|<span data-ttu-id="aec0e-109">부트스트랩 토큰이 세션 토큰에 포함 되어야 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="aec0e-109">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="aec0e-110">`saveBootstrapContext`요소에 대 한 특성을 설정 하 여 토큰 처리기 컬렉션에서 값을 설정할 수도 있습니다 [\<identityConfiguration>](identityconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="aec0e-110">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="aec0e-111">토큰 처리기 컬렉션에 설정 된 값은 서비스에 설정 된 값을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="aec0e-111">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="aec0e-112">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="aec0e-112">maximumClockSkew</span></span>|<span data-ttu-id="aec0e-113"><xref:System.TimeSpan>허용 되는 최대 클록 오차를 지정 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="aec0e-113">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="aec0e-114">로그인 세션이 만료 시간 유효성 검사와 같은 시간에 민감한 작업을 수행할 때 허용 되는 최대 클럭 오차를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="aec0e-114">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="aec0e-115">기본값은 5 분 "00:05:00"입니다.</span><span class="sxs-lookup"><span data-stu-id="aec0e-115">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="aec0e-116">값을 지정 하는 방법에 대 한 자세한 내용은 <xref:System.TimeSpan> [Timespan 값](../windows-workflow-foundation/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aec0e-116">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="aec0e-117">요소의 특성을 설정 하 여 서비스 수준에서 최대 클록 오차를 설정할 수도 있습니다 `maximumClockSkew` [\<identityConfiguration>](identityconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="aec0e-117">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="aec0e-118">토큰 처리기 컬렉션에 설정 된 값은 서비스에 설정 된 값을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="aec0e-118">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aec0e-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="aec0e-119">Child Elements</span></span>  
  
|<span data-ttu-id="aec0e-120">요소</span><span class="sxs-lookup"><span data-stu-id="aec0e-120">Element</span></span>|<span data-ttu-id="aec0e-121">설명</span><span class="sxs-lookup"><span data-stu-id="aec0e-121">Description</span></span>|  
|-------------|-----------------|  
|[\<audienceUris>](audienceuris.md)|<span data-ttu-id="aec0e-122">이 신뢰 당사자의 허용 되는 식별자에 해당 하는 Uri 집합을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="aec0e-122">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="aec0e-123">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="aec0e-123">Optional.</span></span>|  
|[\<caches>](caches.md)|<span data-ttu-id="aec0e-124">세션 토큰 및 토큰 재생 검색에 사용 되는 캐시를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="aec0e-124">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="aec0e-125">는 서비스 수준 또는 보안 토큰 처리기 컬렉션에서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aec0e-125">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="aec0e-126">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="aec0e-126">Optional.</span></span>|  
|[\<certificateValidation>](certificatevalidation.md)|<span data-ttu-id="aec0e-127">토큰 처리기에서 인증서의 유효성을 검사 하는 데 사용 하는 설정을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="aec0e-127">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="aec0e-128">는 서비스 수준 또는 보안 토큰 처리기 컬렉션에서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aec0e-128">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="aec0e-129">이러한 설정은 고유한 유효성 검사기를 사용 하 여 특정 처리기를 구성 하는 경우 재정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aec0e-129">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="aec0e-130">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="aec0e-130">Optional.</span></span>|  
|[\<issuerNameRegistry>](issuernameregistry.md)|<span data-ttu-id="aec0e-131">토큰 처리기 컬렉션의 처리기에서 사용 하는 발급자 이름 레지스트리를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="aec0e-131">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="aec0e-132">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="aec0e-132">Optional.</span></span>|  
|[\<issuerTokenResolver>](issuertokenresolver.md)|<span data-ttu-id="aec0e-133">토큰 처리기 컬렉션의 처리기에서 사용 하는 발급자 토큰 확인자를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="aec0e-133">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="aec0e-134">발급자 토큰 확인자는 들어오는 토큰과 메시지의 서명 토큰을 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aec0e-134">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="aec0e-135">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="aec0e-135">Optional.</span></span>|  
|[\<serviceTokenResolver>](servicetokenresolver.md)|<span data-ttu-id="aec0e-136">토큰 처리기 컬렉션의 처리기에서 사용 하는 서비스 토큰 확인자를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="aec0e-136">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="aec0e-137">서비스 토큰 확인자는 들어오는 토큰과 메시지의 암호화 토큰을 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aec0e-137">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="aec0e-138">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="aec0e-138">Optional.</span></span>|  
|[\<tokenReplayDetection>](tokenreplaydetection.md)|<span data-ttu-id="aec0e-139">토큰 재생 검색을 사용 하도록 설정 하 고 토큰의 만료 시간을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="aec0e-139">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="aec0e-140">는 서비스 수준 또는 보안 토큰 처리기 컬렉션에서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aec0e-140">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="aec0e-141">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="aec0e-141">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aec0e-142">부모 요소</span><span class="sxs-lookup"><span data-stu-id="aec0e-142">Parent Elements</span></span>  
  
|<span data-ttu-id="aec0e-143">요소</span><span class="sxs-lookup"><span data-stu-id="aec0e-143">Element</span></span>|<span data-ttu-id="aec0e-144">설명</span><span class="sxs-lookup"><span data-stu-id="aec0e-144">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|<span data-ttu-id="aec0e-145">끝점에 등록 된 보안 토큰 처리기의 컬렉션을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="aec0e-145">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aec0e-146">설명</span><span class="sxs-lookup"><span data-stu-id="aec0e-146">Remarks</span></span>  

 <span data-ttu-id="aec0e-147">이 섹션에서는 개체의 속성 값을 제공 <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> 합니다.</span><span class="sxs-lookup"><span data-stu-id="aec0e-147">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="aec0e-148">이 섹션에서 구성 된 설정은 서비스에 구성 된 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="aec0e-148">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="aec0e-149">이러한 설정 중 일부는 보안 토큰 처리기 컬렉션에 처리기를 추가할 때 지정 된 설정에 의해 재정의 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aec0e-149">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aec0e-150">예제</span><span class="sxs-lookup"><span data-stu-id="aec0e-150">Example</span></span>  
  
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
