---
description: 다음에 대해 자세히 알아보세요. <securityTokenHandlerConfiguration>
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: 8c014d971d3e8cc640a3b7042e3a0266d902de7d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698312"
---
# \<securityTokenHandlerConfiguration>

<span data-ttu-id="8c4b5-102">토큰 처리기의 컬렉션에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c4b5-102">Provides configuration for the collection of token handlers.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenHandlerConfiguration>**  
  
## <a name="syntax"></a><span data-ttu-id="8c4b5-103">구문</span><span class="sxs-lookup"><span data-stu-id="8c4b5-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c4b5-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8c4b5-104">Attributes and Elements</span></span>  

 <span data-ttu-id="8c4b5-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8c4b5-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c4b5-106">특성</span><span class="sxs-lookup"><span data-stu-id="8c4b5-106">Attributes</span></span>  
  
|<span data-ttu-id="8c4b5-107">attribute</span><span class="sxs-lookup"><span data-stu-id="8c4b5-107">Attribute</span></span>|<span data-ttu-id="8c4b5-108">설명</span><span class="sxs-lookup"><span data-stu-id="8c4b5-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8c4b5-109">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="8c4b5-109">saveBootstrapContext</span></span>|<span data-ttu-id="8c4b5-110">부트스트랩 토큰이 세션 토큰에 포함 되어야 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c4b5-110">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="8c4b5-111">`saveBootstrapContext`요소에 대 한 특성을 설정 하 여 토큰 처리기 컬렉션에서 값을 설정할 수도 있습니다 [\<identityConfiguration>](identityconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="8c4b5-111">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="8c4b5-112">토큰 처리기 컬렉션에 설정 된 값은 서비스에 설정 된 값을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c4b5-112">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="8c4b5-113">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="8c4b5-113">maximumClockSkew</span></span>|<span data-ttu-id="8c4b5-114"><xref:System.TimeSpan>허용 되는 최대 클록 오차를 지정 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="8c4b5-114">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="8c4b5-115">로그인 세션이 만료 시간 유효성 검사와 같은 시간에 민감한 작업을 수행할 때 허용 되는 최대 클럭 오차를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c4b5-115">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="8c4b5-116">기본값은 5 분 "00:05:00"입니다.</span><span class="sxs-lookup"><span data-stu-id="8c4b5-116">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="8c4b5-117">값을 지정 하는 방법에 대 한 자세한 내용은 <xref:System.TimeSpan> [Timespan 값](../windows-workflow-foundation/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8c4b5-117">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="8c4b5-118">요소의 특성을 설정 하 여 서비스 수준에서 최대 클록 오차를 설정할 수도 있습니다 `maximumClockSkew` [\<identityConfiguration>](identityconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="8c4b5-118">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="8c4b5-119">토큰 처리기 컬렉션에 설정 된 값은 서비스에 설정 된 값을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c4b5-119">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8c4b5-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8c4b5-120">Child Elements</span></span>  
  
|<span data-ttu-id="8c4b5-121">요소</span><span class="sxs-lookup"><span data-stu-id="8c4b5-121">Element</span></span>|<span data-ttu-id="8c4b5-122">설명</span><span class="sxs-lookup"><span data-stu-id="8c4b5-122">Description</span></span>|  
|-------------|-----------------|  
|[\<audienceUris>](audienceuris.md)|<span data-ttu-id="8c4b5-123">이 신뢰 당사자의 허용 되는 식별자에 해당 하는 Uri 집합을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c4b5-123">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="8c4b5-124">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8c4b5-124">Optional.</span></span>|  
|[\<caches>](caches.md)|<span data-ttu-id="8c4b5-125">세션 토큰 및 토큰 재생 검색에 사용 되는 캐시를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c4b5-125">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="8c4b5-126">는 서비스 수준 또는 보안 토큰 처리기 컬렉션에서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c4b5-126">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="8c4b5-127">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8c4b5-127">Optional.</span></span>|  
|[\<certificateValidation>](certificatevalidation.md)|<span data-ttu-id="8c4b5-128">토큰 처리기에서 인증서의 유효성을 검사 하는 데 사용 하는 설정을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c4b5-128">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="8c4b5-129">는 서비스 수준 또는 보안 토큰 처리기 컬렉션에서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c4b5-129">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="8c4b5-130">이러한 설정은 고유한 유효성 검사기를 사용 하 여 특정 처리기를 구성 하는 경우 재정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c4b5-130">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="8c4b5-131">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8c4b5-131">Optional.</span></span>|  
|[\<issuerNameRegistry>](issuernameregistry.md)|<span data-ttu-id="8c4b5-132">토큰 처리기 컬렉션의 처리기에서 사용 하는 발급자 이름 레지스트리를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c4b5-132">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="8c4b5-133">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8c4b5-133">Optional.</span></span>|  
|[\<issuerTokenResolver>](issuertokenresolver.md)|<span data-ttu-id="8c4b5-134">토큰 처리기 컬렉션의 처리기에서 사용 하는 발급자 토큰 확인자를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c4b5-134">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="8c4b5-135">발급자 토큰 확인자는 들어오는 토큰과 메시지의 서명 토큰을 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c4b5-135">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="8c4b5-136">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8c4b5-136">Optional.</span></span>|  
|[\<serviceTokenResolver>](servicetokenresolver.md)|<span data-ttu-id="8c4b5-137">토큰 처리기 컬렉션의 처리기에서 사용 하는 서비스 토큰 확인자를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c4b5-137">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="8c4b5-138">서비스 토큰 확인자는 들어오는 토큰과 메시지의 암호화 토큰을 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c4b5-138">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="8c4b5-139">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8c4b5-139">Optional.</span></span>|  
|[\<tokenReplayDetection>](tokenreplaydetection.md)|<span data-ttu-id="8c4b5-140">토큰 재생 검색을 사용 하도록 설정 하 고 토큰의 만료 시간을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c4b5-140">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="8c4b5-141">는 서비스 수준 또는 보안 토큰 처리기 컬렉션에서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c4b5-141">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="8c4b5-142">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8c4b5-142">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8c4b5-143">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8c4b5-143">Parent Elements</span></span>  
  
|<span data-ttu-id="8c4b5-144">요소</span><span class="sxs-lookup"><span data-stu-id="8c4b5-144">Element</span></span>|<span data-ttu-id="8c4b5-145">설명</span><span class="sxs-lookup"><span data-stu-id="8c4b5-145">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|<span data-ttu-id="8c4b5-146">끝점에 등록 된 보안 토큰 처리기의 컬렉션을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c4b5-146">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c4b5-147">설명</span><span class="sxs-lookup"><span data-stu-id="8c4b5-147">Remarks</span></span>  

 <span data-ttu-id="8c4b5-148">이 섹션에서는 개체의 속성 값을 제공 <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c4b5-148">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="8c4b5-149">이 섹션에서 구성 된 설정은 서비스에 구성 된 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c4b5-149">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="8c4b5-150">이러한 설정 중 일부는 보안 토큰 처리기 컬렉션에 처리기를 추가할 때 지정 된 설정에 의해 재정의 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c4b5-150">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c4b5-151">예제</span><span class="sxs-lookup"><span data-stu-id="8c4b5-151">Example</span></span>  
  
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
