---
title: <trustedIssuers>
ms.date: 03/30/2017
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
author: BrucePerlerMS
ms.openlocfilehash: cebfc2f3598f32f233db6039dfe82076d2ffce46
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59221706"
---
# <a name="trustedissuers"></a><span data-ttu-id="aec2c-101">\<trustedIssuers></span><span class="sxs-lookup"><span data-stu-id="aec2c-101">\<trustedIssuers></span></span>
<span data-ttu-id="aec2c-102">구성 기반 발급자 이름 레지스트리에 사용 되는 신뢰할 수 있는 발급자 인증서의 목록 구성 (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span><span class="sxs-lookup"><span data-stu-id="aec2c-102">Configures the list of trusted issuer certificates used by the configuration-based issuer name registry (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span></span>  
  
 <span data-ttu-id="aec2c-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="aec2c-103">\<system.identityModel></span></span>  
<span data-ttu-id="aec2c-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="aec2c-104">\<identityConfiguration></span></span>  
<span data-ttu-id="aec2c-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="aec2c-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="aec2c-106">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="aec2c-106">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="aec2c-107">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="aec2c-107">\<issuerNameRegistry></span></span>  
<span data-ttu-id="aec2c-108">\<trustedIssuers></span><span class="sxs-lookup"><span data-stu-id="aec2c-108">\<trustedIssuers></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aec2c-109">구문</span><span class="sxs-lookup"><span data-stu-id="aec2c-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aec2c-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="aec2c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="aec2c-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="aec2c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aec2c-112">특성</span><span class="sxs-lookup"><span data-stu-id="aec2c-112">Attributes</span></span>  
 <span data-ttu-id="aec2c-113">없음</span><span class="sxs-lookup"><span data-stu-id="aec2c-113">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="aec2c-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="aec2c-114">Child Elements</span></span>  
  
|<span data-ttu-id="aec2c-115">요소</span><span class="sxs-lookup"><span data-stu-id="aec2c-115">Element</span></span>|<span data-ttu-id="aec2c-116">설명</span><span class="sxs-lookup"><span data-stu-id="aec2c-116">Description</span></span>|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|<span data-ttu-id="aec2c-117">신뢰할 수 있는 발급자의 컬렉션에 인증서를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="aec2c-117">Adds a certificate to the collection of trusted issuers.</span></span> <span data-ttu-id="aec2c-118">인증서가 지정 된 된 `thumbprint` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="aec2c-118">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="aec2c-119">이 특성은 필수 이며 인증서 지 문의 ASN.1 인코딩된 폼을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aec2c-119">This attribute is required and should contain the ASN.1 encoded form of the certificate thumbprint.</span></span> <span data-ttu-id="aec2c-120">`name` 특성은 선택적 이며 인증서에 대 한 친숙 한 이름을 지정 하려면 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aec2c-120">The `name` attribute is optional and can be used to specify a friendly name for the certificate.</span></span>|  
|`<clear>`|<span data-ttu-id="aec2c-121">신뢰할 수 있는 발급자의 컬렉션에서 모든 인증서를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="aec2c-121">Clears all certificates from the collection of trusted issuers.</span></span>|  
|`<remove thumbprint=xs:string>`|<span data-ttu-id="aec2c-122">신뢰할 수 있는 발급자의 컬렉션에서 인증서를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="aec2c-122">Removes a certificate from the collection of trusted issuers.</span></span> <span data-ttu-id="aec2c-123">인증서가 지정 된 된 `thumbprint` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="aec2c-123">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="aec2c-124">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="aec2c-124">This attribute is required.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aec2c-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="aec2c-125">Parent Elements</span></span>  
  
|<span data-ttu-id="aec2c-126">요소</span><span class="sxs-lookup"><span data-stu-id="aec2c-126">Element</span></span>|<span data-ttu-id="aec2c-127">설명</span><span class="sxs-lookup"><span data-stu-id="aec2c-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aec2c-128">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="aec2c-128">\<issuerNameRegistry></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|<span data-ttu-id="aec2c-129">발급자 이름 레지스트리를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="aec2c-129">Configures the issuer name registry.</span></span> <span data-ttu-id="aec2c-130">**중요:**  `type` 특성을 `<issuerNameRegistry>` 요소를 참조 해야 합니다를 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> 클래스를 `<trustedIssuers>` 유효한 요소.</span><span class="sxs-lookup"><span data-stu-id="aec2c-130">**Important:**  The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aec2c-131">설명</span><span class="sxs-lookup"><span data-stu-id="aec2c-131">Remarks</span></span>  
 <span data-ttu-id="aec2c-132">Windows Identity Foundation (WIF)의 단일 구현을 제공 합니다 <xref:System.IdentityModel.Tokens.IssuerNameRegistry> 기본적으로 클래스는 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="aec2c-132">Windows Identity Foundation (WIF) provides a single implementation of the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="aec2c-133">구성 발급자 이름 레지스트리 구성에서 로드 되는 신뢰할 수 있는 발급자 목록을 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="aec2c-133">The configuration issuer name registry maintains a list of trusted issuers that is loaded from configuration.</span></span> <span data-ttu-id="aec2c-134">각 발급자 이름은 X.509 인증서 발급자가 생성 한 토큰의 서명을 확인 하는 데 필요한 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="aec2c-134">The list associates each issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by the issuer.</span></span> <span data-ttu-id="aec2c-135">신뢰할 수 있는 발급자 인증서 목록에서 지정 된 `<trustedIssuers>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="aec2c-135">The list of trusted issuer certificates is specified under the `<trustedIssuers>` element.</span></span> <span data-ttu-id="aec2c-136">목록의 각 요소는 해당 발급자가 생성 한 토큰의 서명을 확인 하는 데 필요한 X.509 인증서를 사용 하 여 니모닉 발급자 이름을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="aec2c-136">Each element in the list associates a mnemonic issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by that issuer.</span></span> <span data-ttu-id="aec2c-137">인증서의 인증서 지문 인코딩된 ASN.1를 사용 하 여 지정 되 고 사용 하 여 컬렉션을 추가 하는 신뢰할 수 있는 `<add>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="aec2c-137">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added the collection by using `<add>` element.</span></span> <span data-ttu-id="aec2c-138">지우거 나 목록에서 발급자 (인증서)를 사용 하 여 제거할 수 있습니다 합니다 `<clear>` 고 `<remove>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="aec2c-138">You can clear or remove issuers (certificates) from the list by using the `<clear>` and `<remove>` elements.</span></span>  
  
 <span data-ttu-id="aec2c-139">`type` 특성을 `<issuerNameRegistry>` 요소를 참조 해야 합니다를 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> 클래스를 `<trustedIssuers>` 유효한 요소.</span><span class="sxs-lookup"><span data-stu-id="aec2c-139">The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aec2c-140">예제</span><span class="sxs-lookup"><span data-stu-id="aec2c-140">Example</span></span>  
 <span data-ttu-id="aec2c-141">다음 XML 기반 구성을 발급자를 지정 하는 방법을 이름 레지스트리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aec2c-141">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="aec2c-142">참고자료</span><span class="sxs-lookup"><span data-stu-id="aec2c-142">See also</span></span>

- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
