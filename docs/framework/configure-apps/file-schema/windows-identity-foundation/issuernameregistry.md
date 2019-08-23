---
title: <issuerNameRegistry>
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
ms.openlocfilehash: d0a1f8dd0c29aaee56c2ca1162cc70cc1e5ed106
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942676"
---
# <a name="issuernameregistry"></a><span data-ttu-id="879b7-101">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="879b7-101">\<issuerNameRegistry></span></span>
<span data-ttu-id="879b7-102">토큰 처리기 컬렉션의 처리기에서 사용 하는 발급자 이름 레지스트리를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="879b7-102">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span>  
  
 <span data-ttu-id="879b7-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="879b7-103">\<system.identityModel></span></span>  
<span data-ttu-id="879b7-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="879b7-104">\<identityConfiguration></span></span>  
<span data-ttu-id="879b7-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="879b7-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="879b7-106">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="879b7-106">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="879b7-107">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="879b7-107">\<issuerNameRegistry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="879b7-108">구문</span><span class="sxs-lookup"><span data-stu-id="879b7-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerNameRegistry type=xs:string>  
          <optionalCustomConfigurationElements />  
        </issuerNameRegistry>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="879b7-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="879b7-109">Attributes and Elements</span></span>  
 <span data-ttu-id="879b7-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="879b7-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="879b7-111">특성</span><span class="sxs-lookup"><span data-stu-id="879b7-111">Attributes</span></span>  
  
|<span data-ttu-id="879b7-112">특성</span><span class="sxs-lookup"><span data-stu-id="879b7-112">Attribute</span></span>|<span data-ttu-id="879b7-113">Description</span><span class="sxs-lookup"><span data-stu-id="879b7-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="879b7-114">type</span><span class="sxs-lookup"><span data-stu-id="879b7-114">type</span></span>|<span data-ttu-id="879b7-115"><xref:System.IdentityModel.Tokens.IssuerNameRegistry> 클래스에서 파생 되는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="879b7-115">A type that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="879b7-116">사용자 지정 `type`을 지정 하는 방법에 대 한 자세한 내용은 [사용자 지정 형식 참조]를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="879b7-116">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="879b7-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="879b7-117">Child Elements</span></span>  
  
|<span data-ttu-id="879b7-118">요소</span><span class="sxs-lookup"><span data-stu-id="879b7-118">Element</span></span>|<span data-ttu-id="879b7-119">Description</span><span class="sxs-lookup"><span data-stu-id="879b7-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="879b7-120">\<trustedIssuers></span><span class="sxs-lookup"><span data-stu-id="879b7-120">\<trustedIssuers></span></span>](trustedissuers.md)|<span data-ttu-id="879b7-121">특성이 구성 기반 발급자 이름 레지스트리 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> (클래스)를 [ \<](trustedissuers.md) 지정 하는 경우 s > 요소를 지정 해야 합니다. `type`</span><span class="sxs-lookup"><span data-stu-id="879b7-121">When the `type` attribute specifies the configuration-based issuer name registry (the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class), the [\<trustedIssuers>](trustedissuers.md) element must be specified.</span></span> <span data-ttu-id="879b7-122">[ \<S >](trustedissuers.md) 요소는, 또는 `<add>`요소를 `<clear>`자식 요소로사용할수있습니다`<remove>` .</span><span class="sxs-lookup"><span data-stu-id="879b7-122">The [\<trustedIssuers>](trustedissuers.md) element can take `<add>`, `<clear>`, or `<remove>` elements as child elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="879b7-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="879b7-123">Parent Elements</span></span>  
  
|<span data-ttu-id="879b7-124">요소</span><span class="sxs-lookup"><span data-stu-id="879b7-124">Element</span></span>|<span data-ttu-id="879b7-125">Description</span><span class="sxs-lookup"><span data-stu-id="879b7-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="879b7-126">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="879b7-126">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="879b7-127">보안 토큰 처리기의 컬렉션에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="879b7-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="879b7-128">설명</span><span class="sxs-lookup"><span data-stu-id="879b7-128">Remarks</span></span>  
 <span data-ttu-id="879b7-129">발급자 이름 레지스트리를 사용 하 여 모든 발급자 토큰의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="879b7-129">All issuer tokens are validated using an issuer name registry.</span></span> <span data-ttu-id="879b7-130"><xref:System.IdentityModel.Tokens.IssuerNameRegistry> 클래스에서 파생 되는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="879b7-130">This is an object that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="879b7-131">발급자 이름 레지스트리는 니모닉 이름을 해당 발급자가 생성 한 토큰의 서명을 확인 하는 데 필요한 암호화 자료에 연결 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="879b7-131">The issuer name registry is used to associate a mnemonic name to the cryptographic material that is needed to verify the signatures of tokens produced by the corresponding issuer.</span></span> <span data-ttu-id="879b7-132">발급자 이름 레지스트리는 RP (신뢰 당사자) 응용 프로그램에서 신뢰할 수 있는 발급자 목록을 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="879b7-132">The issuer name registry maintains a list of issuers that are trusted by the relying party (RP) application.</span></span> <span data-ttu-id="879b7-133">발급자 이름 레지스트리의 형식은 특성을 `type` 사용 하 여 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="879b7-133">The type of the issuer name registry is specified using the `type` attribute.</span></span> <span data-ttu-id="879b7-134">요소 `<issuerNameRegistry>` 는 지정 된 형식에 대 한 구성을 제공 하는 하나 이상의 자식 요소를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="879b7-134">The `<issuerNameRegistry>` element can have one or more child elements that provide configuration for the specified type.</span></span> <span data-ttu-id="879b7-135">메서드를 <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> 재정의 하 여 이러한 자식 요소를 처리 하는 논리를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="879b7-135">You provide the logic that processes these child elements by overriding the <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> method.</span></span>  
  
 <span data-ttu-id="879b7-136">WIF은 기본적으로 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> 클래스의 단일 발급자 이름 레지스트리 유형을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="879b7-136">WIF provides a single issuer name registry type out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="879b7-137">이 클래스는 구성에 지정 된 신뢰할 수 있는 발급자 인증서 집합을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="879b7-137">This class uses a set of trusted issuer certificates that are specified in configuration.</span></span> <span data-ttu-id="879b7-138">여기에는 신뢰할 수 있는 발급자 `<trustedIssuers>`인증서의 컬렉션을 구성 하는 자식 구성 요소가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="879b7-138">It requires a child configuration element, `<trustedIssuers>`, under which the collection of trusted issuer certificates is configured.</span></span> <span data-ttu-id="879b7-139">신뢰할 수 있는 인증서는 ASN으로 인코딩된 인증서 지문 형태를 사용 하 여 지정 되며, 또는 `<add>` `<remove>` 요소를 `<clear>`사용 하 여 컬렉션에서 추가 되거나 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="879b7-139">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added or removed from the collection by using `<add>`, `<clear>`, or `<remove>` elements.</span></span>  
  
 <span data-ttu-id="879b7-140">합니다 `<issuerNameRegistry>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="879b7-140">The `<issuerNameRegistry>` element is represented by the <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="879b7-141">IdentityConfiguration > 요소의 자식 요소로 `<issuerNameRegistry>` [요소를 지정 하는 것은 더 이상 사용 되지 않지만 이전 버전과의 호환성을 위해 \<](identityconfiguration.md) 계속 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="879b7-141">Specifying the `<issuerNameRegistry>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="879b7-142">요소의 설정은 `<identityConfiguration>` 요소의 설정을 재정의 합니다. `<securityTokenHandlerConfiguration>`</span><span class="sxs-lookup"><span data-stu-id="879b7-142">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="879b7-143">예제</span><span class="sxs-lookup"><span data-stu-id="879b7-143">Example</span></span>  
 <span data-ttu-id="879b7-144">다음 XML에서는 구성 기반 발급자 이름 레지스트리를 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="879b7-144">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="879b7-145">참고자료</span><span class="sxs-lookup"><span data-stu-id="879b7-145">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
