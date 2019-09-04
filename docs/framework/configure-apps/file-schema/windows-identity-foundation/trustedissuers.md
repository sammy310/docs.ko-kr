---
title: <trustedIssuers>
ms.date: 03/30/2017
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
author: BrucePerlerMS
ms.openlocfilehash: 50fc7194823fb0c5c426fb54ffd50b17c3714ed9
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251752"
---
# <a name="trustedissuers"></a><span data-ttu-id="ae591-101">\<trustedIssuers></span><span class="sxs-lookup"><span data-stu-id="ae591-101">\<trustedIssuers></span></span>
<span data-ttu-id="ae591-102">구성 기반 발급자 이름 레지스트리 (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>)에서 사용 하는 신뢰할 수 있는 발급자 인증서 목록을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae591-102">Configures the list of trusted issuer certificates used by the configuration-based issuer name registry (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span></span>  
  
<span data-ttu-id="ae591-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ae591-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ae591-104">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="ae591-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="ae591-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="ae591-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="ae591-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="ae591-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="ae591-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlerConfiguration >** ](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="ae591-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="ae591-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<issuerNameRegistry >** ](issuernameregistry.md)</span><span class="sxs-lookup"><span data-stu-id="ae591-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuerNameRegistry>**](issuernameregistry.md)</span></span>\
<span data-ttu-id="ae591-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<s >**</span><span class="sxs-lookup"><span data-stu-id="ae591-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<trustedIssuers>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae591-110">구문</span><span class="sxs-lookup"><span data-stu-id="ae591-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerNameRegistry>  
          <trustedIssuers>  
            <add thumbprint=xs:string name=xs:string>  
            <clear>  
            <remove thumbprint=xs:string>  
          </trustedIssuers>  
        </issuerNameRegistry>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ae591-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ae591-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ae591-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ae591-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ae591-113">특성</span><span class="sxs-lookup"><span data-stu-id="ae591-113">Attributes</span></span>  
 <span data-ttu-id="ae591-114">없음</span><span class="sxs-lookup"><span data-stu-id="ae591-114">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ae591-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ae591-115">Child Elements</span></span>  
  
|<span data-ttu-id="ae591-116">요소</span><span class="sxs-lookup"><span data-stu-id="ae591-116">Element</span></span>|<span data-ttu-id="ae591-117">설명</span><span class="sxs-lookup"><span data-stu-id="ae591-117">Description</span></span>|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|<span data-ttu-id="ae591-118">신뢰할 수 있는 발급자 컬렉션에 인증서를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae591-118">Adds a certificate to the collection of trusted issuers.</span></span> <span data-ttu-id="ae591-119">인증서는 `thumbprint` 특성을 사용 하 여 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae591-119">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="ae591-120">이 특성은 필수 이며, asn.1.1로 인코딩된 인증서 지문 형식을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae591-120">This attribute is required and should contain the ASN.1 encoded form of the certificate thumbprint.</span></span> <span data-ttu-id="ae591-121">특성 `name` 은 선택 사항이 며 인증서의 이름을 지정 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae591-121">The `name` attribute is optional and can be used to specify a friendly name for the certificate.</span></span>|  
|`<clear>`|<span data-ttu-id="ae591-122">신뢰할 수 있는 발급자 컬렉션에서 모든 인증서를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="ae591-122">Clears all certificates from the collection of trusted issuers.</span></span>|  
|`<remove thumbprint=xs:string>`|<span data-ttu-id="ae591-123">신뢰할 수 있는 발급자 컬렉션에서 인증서를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae591-123">Removes a certificate from the collection of trusted issuers.</span></span> <span data-ttu-id="ae591-124">인증서는 `thumbprint` 특성을 사용 하 여 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae591-124">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="ae591-125">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="ae591-125">This attribute is required.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ae591-126">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ae591-126">Parent Elements</span></span>  
  
|<span data-ttu-id="ae591-127">요소</span><span class="sxs-lookup"><span data-stu-id="ae591-127">Element</span></span>|<span data-ttu-id="ae591-128">Description</span><span class="sxs-lookup"><span data-stu-id="ae591-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ae591-129">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="ae591-129">\<issuerNameRegistry></span></span>](issuernameregistry.md)|<span data-ttu-id="ae591-130">발급자 이름 레지스트리를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae591-130">Configures the issuer name registry.</span></span> <span data-ttu-id="ae591-131">**중요:**  요소의 `type` 특성 `<issuerNameRegistry>` 은 `<trustedIssuers>` 요소에 대 한 클래스 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> 를 참조 해야 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae591-131">**Important:**  The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae591-132">설명</span><span class="sxs-lookup"><span data-stu-id="ae591-132">Remarks</span></span>  
 <span data-ttu-id="ae591-133">WIF (Windows Identity Foundation)는 클래스의 단일 구현을 <xref:System.IdentityModel.Tokens.IssuerNameRegistry> <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> 제공 합니다. 클래스는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="ae591-133">Windows Identity Foundation (WIF) provides a single implementation of the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="ae591-134">구성 발급자 이름 레지스트리는 구성에서 로드 되는 신뢰할 수 있는 발급자의 목록을 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae591-134">The configuration issuer name registry maintains a list of trusted issuers that is loaded from configuration.</span></span> <span data-ttu-id="ae591-135">목록은 각 발급자 이름을 발급자가 생성 한 토큰의 서명을 확인 하는 데 필요한 x.509 인증서와 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae591-135">The list associates each issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by the issuer.</span></span> <span data-ttu-id="ae591-136">신뢰할 수 있는 발급자 인증서의 목록은 `<trustedIssuers>` 요소 아래에 지정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae591-136">The list of trusted issuer certificates is specified under the `<trustedIssuers>` element.</span></span> <span data-ttu-id="ae591-137">목록의 각 요소는 니모닉 발급자 이름과 해당 발급자가 생성 한 토큰의 서명을 확인 하는 데 필요한 x.509 인증서를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae591-137">Each element in the list associates a mnemonic issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by that issuer.</span></span> <span data-ttu-id="ae591-138">신뢰할 수 있는 인증서는 asn.1로 인코딩된 인증서 지문 형태를 사용 하 여 지정 되 고 요소를 사용 `<add>` 하 여 컬렉션에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae591-138">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added the collection by using `<add>` element.</span></span> <span data-ttu-id="ae591-139">`<clear>` 및`<remove>` 요소를 사용 하 여 목록에서 발급자 (인증서)를 지우거 나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae591-139">You can clear or remove issuers (certificates) from the list by using the `<clear>` and `<remove>` elements.</span></span>  
  
 <span data-ttu-id="ae591-140">요소의 `type` 특성 `<issuerNameRegistry>` 은 `<trustedIssuers>` 요소에 대 한 클래스 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> 를 참조 해야 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae591-140">The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae591-141">예제</span><span class="sxs-lookup"><span data-stu-id="ae591-141">Example</span></span>  
 <span data-ttu-id="ae591-142">다음 XML에서는 구성 기반 발급자 이름 레지스트리를 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ae591-142">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ae591-143">참고자료</span><span class="sxs-lookup"><span data-stu-id="ae591-143">See also</span></span>

- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
