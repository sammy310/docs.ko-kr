---
description: 다음에 대해 자세히 알아보세요. <issuerNameRegistry>
title: <issuerNameRegistry>
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
ms.openlocfilehash: 73eb0d9d4d19f8e25f2db501e8cb3858d346ac2c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803856"
---
# \<issuerNameRegistry>

<span data-ttu-id="9c2eb-102">토큰 처리기 컬렉션의 처리기에서 사용 하는 발급자 이름 레지스트리를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c2eb-102">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerNameRegistry>**  
  
## <a name="syntax"></a><span data-ttu-id="9c2eb-103">구문</span><span class="sxs-lookup"><span data-stu-id="9c2eb-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9c2eb-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9c2eb-104">Attributes and Elements</span></span>  

 <span data-ttu-id="9c2eb-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9c2eb-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9c2eb-106">특성</span><span class="sxs-lookup"><span data-stu-id="9c2eb-106">Attributes</span></span>  
  
|<span data-ttu-id="9c2eb-107">attribute</span><span class="sxs-lookup"><span data-stu-id="9c2eb-107">Attribute</span></span>|<span data-ttu-id="9c2eb-108">Description</span><span class="sxs-lookup"><span data-stu-id="9c2eb-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9c2eb-109">type</span><span class="sxs-lookup"><span data-stu-id="9c2eb-109">type</span></span>|<span data-ttu-id="9c2eb-110">클래스에서 파생 되는 형식 <xref:System.IdentityModel.Tokens.IssuerNameRegistry> 입니다.</span><span class="sxs-lookup"><span data-stu-id="9c2eb-110">A type that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="9c2eb-111">사용자 지정을 지정 하는 방법에 대 한 자세한 내용은 `type` [사용자 지정 형식 참조]를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9c2eb-111">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9c2eb-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9c2eb-112">Child Elements</span></span>  
  
|<span data-ttu-id="9c2eb-113">요소</span><span class="sxs-lookup"><span data-stu-id="9c2eb-113">Element</span></span>|<span data-ttu-id="9c2eb-114">설명</span><span class="sxs-lookup"><span data-stu-id="9c2eb-114">Description</span></span>|  
|-------------|-----------------|  
|[\<trustedIssuers>](trustedissuers.md)|<span data-ttu-id="9c2eb-115">`type`특성이 구성 기반 발급자 이름 레지스트리 (클래스)를 지정 하는 경우 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> 요소를 [\<trustedIssuers>](trustedissuers.md) 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c2eb-115">When the `type` attribute specifies the configuration-based issuer name registry (the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class), the [\<trustedIssuers>](trustedissuers.md) element must be specified.</span></span> <span data-ttu-id="9c2eb-116">[\<trustedIssuers>](trustedissuers.md)요소는 `<add>` , `<clear>` 또는 요소를 자식 요소로 사용할 수 있습니다 `<remove>` .</span><span class="sxs-lookup"><span data-stu-id="9c2eb-116">The [\<trustedIssuers>](trustedissuers.md) element can take `<add>`, `<clear>`, or `<remove>` elements as child elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9c2eb-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9c2eb-117">Parent Elements</span></span>  
  
|<span data-ttu-id="9c2eb-118">요소</span><span class="sxs-lookup"><span data-stu-id="9c2eb-118">Element</span></span>|<span data-ttu-id="9c2eb-119">설명</span><span class="sxs-lookup"><span data-stu-id="9c2eb-119">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="9c2eb-120">보안 토큰 처리기의 컬렉션에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c2eb-120">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c2eb-121">설명</span><span class="sxs-lookup"><span data-stu-id="9c2eb-121">Remarks</span></span>  

 <span data-ttu-id="9c2eb-122">발급자 이름 레지스트리를 사용 하 여 모든 발급자 토큰의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c2eb-122">All issuer tokens are validated using an issuer name registry.</span></span> <span data-ttu-id="9c2eb-123">클래스에서 파생 되는 개체입니다 <xref:System.IdentityModel.Tokens.IssuerNameRegistry> .</span><span class="sxs-lookup"><span data-stu-id="9c2eb-123">This is an object that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="9c2eb-124">발급자 이름 레지스트리는 니모닉 이름을 해당 발급자가 생성 한 토큰의 서명을 확인 하는 데 필요한 암호화 자료에 연결 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c2eb-124">The issuer name registry is used to associate a mnemonic name to the cryptographic material that is needed to verify the signatures of tokens produced by the corresponding issuer.</span></span> <span data-ttu-id="9c2eb-125">발급자 이름 레지스트리는 RP (신뢰 당사자) 응용 프로그램에서 신뢰할 수 있는 발급자 목록을 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c2eb-125">The issuer name registry maintains a list of issuers that are trusted by the relying party (RP) application.</span></span> <span data-ttu-id="9c2eb-126">발급자 이름 레지스트리의 형식은 특성을 사용 하 여 지정 합니다 `type` .</span><span class="sxs-lookup"><span data-stu-id="9c2eb-126">The type of the issuer name registry is specified using the `type` attribute.</span></span> <span data-ttu-id="9c2eb-127">`<issuerNameRegistry>`요소는 지정 된 형식에 대 한 구성을 제공 하는 하나 이상의 자식 요소를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c2eb-127">The `<issuerNameRegistry>` element can have one or more child elements that provide configuration for the specified type.</span></span> <span data-ttu-id="9c2eb-128">메서드를 재정의 하 여 이러한 자식 요소를 처리 하는 논리를 제공 합니다 <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> .</span><span class="sxs-lookup"><span data-stu-id="9c2eb-128">You provide the logic that processes these child elements by overriding the <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> method.</span></span>  
  
 <span data-ttu-id="9c2eb-129">WIF은 기본적으로 클래스의 단일 발급자 이름 레지스트리 유형을 제공 합니다 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> .</span><span class="sxs-lookup"><span data-stu-id="9c2eb-129">WIF provides a single issuer name registry type out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="9c2eb-130">이 클래스는 구성에 지정 된 신뢰할 수 있는 발급자 인증서 집합을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c2eb-130">This class uses a set of trusted issuer certificates that are specified in configuration.</span></span> <span data-ttu-id="9c2eb-131">여기에는 `<trustedIssuers>` 신뢰할 수 있는 발급자 인증서의 컬렉션을 구성 하는 자식 구성 요소가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c2eb-131">It requires a child configuration element, `<trustedIssuers>`, under which the collection of trusted issuer certificates is configured.</span></span> <span data-ttu-id="9c2eb-132">신뢰할 수 있는 인증서는 ASN으로 인코딩된 인증서 지문 형태를 사용 하 여 지정 되며 `<add>` , 또는 요소를 사용 하 여 컬렉션에서 추가 되거나 제거 됩니다 `<clear>` `<remove>` .</span><span class="sxs-lookup"><span data-stu-id="9c2eb-132">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added or removed from the collection by using `<add>`, `<clear>`, or `<remove>` elements.</span></span>  
  
 <span data-ttu-id="9c2eb-133">합니다 `<issuerNameRegistry>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="9c2eb-133">The `<issuerNameRegistry>` element is represented by the <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9c2eb-134">요소를 요소의 자식 요소로 지정 하는 것은 `<issuerNameRegistry>` [\<identityConfiguration>](identityconfiguration.md) 더 이상 사용 되지 않지만 이전 버전과의 호환성을 위해 계속 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c2eb-134">Specifying the `<issuerNameRegistry>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="9c2eb-135">`<securityTokenHandlerConfiguration>`요소의 설정은 요소의 설정을 재정의 `<identityConfiguration>` 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c2eb-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c2eb-136">예제</span><span class="sxs-lookup"><span data-stu-id="9c2eb-136">Example</span></span>  

 <span data-ttu-id="9c2eb-137">다음 XML에서는 구성 기반 발급자 이름 레지스트리를 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9c2eb-137">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9c2eb-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9c2eb-138">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
