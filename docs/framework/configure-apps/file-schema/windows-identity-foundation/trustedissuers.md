---
description: 다음에 대해 자세히 알아보세요. <trustedIssuers>
title: <trustedIssuers>
ms.date: 03/30/2017
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
author: BrucePerlerMS
ms.openlocfilehash: 8789eaa38666e22f6a58b3178103aef4408677b7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786514"
---
# \<trustedIssuers>

<span data-ttu-id="a4a06-102">구성 기반 발급자 이름 레지스트리 ()에서 사용 하는 신뢰할 수 있는 발급자 인증서 목록을 구성 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4a06-102">Configures the list of trusted issuer certificates used by the configuration-based issuer name registry (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuerNameRegistry>**](issuernameregistry.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<trustedIssuers>**  
  
## <a name="syntax"></a><span data-ttu-id="a4a06-103">구문</span><span class="sxs-lookup"><span data-stu-id="a4a06-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a4a06-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a4a06-104">Attributes and Elements</span></span>  

 <span data-ttu-id="a4a06-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a4a06-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a4a06-106">특성</span><span class="sxs-lookup"><span data-stu-id="a4a06-106">Attributes</span></span>  

 <span data-ttu-id="a4a06-107">None</span><span class="sxs-lookup"><span data-stu-id="a4a06-107">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a4a06-108">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a4a06-108">Child Elements</span></span>  
  
|<span data-ttu-id="a4a06-109">요소</span><span class="sxs-lookup"><span data-stu-id="a4a06-109">Element</span></span>|<span data-ttu-id="a4a06-110">설명</span><span class="sxs-lookup"><span data-stu-id="a4a06-110">Description</span></span>|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|<span data-ttu-id="a4a06-111">신뢰할 수 있는 발급자 컬렉션에 인증서를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4a06-111">Adds a certificate to the collection of trusted issuers.</span></span> <span data-ttu-id="a4a06-112">인증서는 특성을 사용 하 여 지정 됩니다 `thumbprint` .</span><span class="sxs-lookup"><span data-stu-id="a4a06-112">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="a4a06-113">이 특성은 필수 이며, asn.1.1로 인코딩된 인증서 지문 형식을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4a06-113">This attribute is required and should contain the ASN.1 encoded form of the certificate thumbprint.</span></span> <span data-ttu-id="a4a06-114">`name`특성은 선택 사항이 며 인증서의 이름을 지정 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4a06-114">The `name` attribute is optional and can be used to specify a friendly name for the certificate.</span></span>|  
|`<clear>`|<span data-ttu-id="a4a06-115">신뢰할 수 있는 발급자 컬렉션에서 모든 인증서를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="a4a06-115">Clears all certificates from the collection of trusted issuers.</span></span>|  
|`<remove thumbprint=xs:string>`|<span data-ttu-id="a4a06-116">신뢰할 수 있는 발급자 컬렉션에서 인증서를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4a06-116">Removes a certificate from the collection of trusted issuers.</span></span> <span data-ttu-id="a4a06-117">인증서는 특성을 사용 하 여 지정 됩니다 `thumbprint` .</span><span class="sxs-lookup"><span data-stu-id="a4a06-117">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="a4a06-118">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="a4a06-118">This attribute is required.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a4a06-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a4a06-119">Parent Elements</span></span>  
  
|<span data-ttu-id="a4a06-120">요소</span><span class="sxs-lookup"><span data-stu-id="a4a06-120">Element</span></span>|<span data-ttu-id="a4a06-121">설명</span><span class="sxs-lookup"><span data-stu-id="a4a06-121">Description</span></span>|  
|-------------|-----------------|  
|[\<issuerNameRegistry>](issuernameregistry.md)|<span data-ttu-id="a4a06-122">발급자 이름 레지스트리를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4a06-122">Configures the issuer name registry.</span></span> <span data-ttu-id="a4a06-123">**중요:**  요소의 `type` 특성은 `<issuerNameRegistry>` <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> 요소에 대 한 클래스를 참조 해야 `<trustedIssuers>` 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4a06-123">**Important:**  The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4a06-124">설명</span><span class="sxs-lookup"><span data-stu-id="a4a06-124">Remarks</span></span>  

 <span data-ttu-id="a4a06-125">WIF (Windows Identity Foundation)는 클래스의 단일 구현을 제공 합니다 <xref:System.IdentityModel.Tokens.IssuerNameRegistry> <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> . 클래스는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="a4a06-125">Windows Identity Foundation (WIF) provides a single implementation of the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="a4a06-126">구성 발급자 이름 레지스트리는 구성에서 로드 되는 신뢰할 수 있는 발급자의 목록을 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4a06-126">The configuration issuer name registry maintains a list of trusted issuers that is loaded from configuration.</span></span> <span data-ttu-id="a4a06-127">목록은 각 발급자 이름을 발급자가 생성 한 토큰의 서명을 확인 하는 데 필요한 x.509 인증서와 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4a06-127">The list associates each issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by the issuer.</span></span> <span data-ttu-id="a4a06-128">신뢰할 수 있는 발급자 인증서의 목록은 요소 아래에 지정 되어 `<trustedIssuers>` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4a06-128">The list of trusted issuer certificates is specified under the `<trustedIssuers>` element.</span></span> <span data-ttu-id="a4a06-129">목록의 각 요소는 니모닉 발급자 이름과 해당 발급자가 생성 한 토큰의 서명을 확인 하는 데 필요한 x.509 인증서를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4a06-129">Each element in the list associates a mnemonic issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by that issuer.</span></span> <span data-ttu-id="a4a06-130">신뢰할 수 있는 인증서는 asn.1로 인코딩된 인증서 지문 형태를 사용 하 여 지정 되 고 요소를 사용 하 여 컬렉션에 추가 됩니다. `<add>`</span><span class="sxs-lookup"><span data-stu-id="a4a06-130">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added the collection by using `<add>` element.</span></span> <span data-ttu-id="a4a06-131">및 요소를 사용 하 여 목록에서 발급자 (인증서)를 지우거 나 제거할 수 있습니다 `<clear>` `<remove>` .</span><span class="sxs-lookup"><span data-stu-id="a4a06-131">You can clear or remove issuers (certificates) from the list by using the `<clear>` and `<remove>` elements.</span></span>  
  
 <span data-ttu-id="a4a06-132">요소의 `type` 특성은 `<issuerNameRegistry>` <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> 요소에 대 한 클래스를 참조 해야 `<trustedIssuers>` 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4a06-132">The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4a06-133">예제</span><span class="sxs-lookup"><span data-stu-id="a4a06-133">Example</span></span>  

 <span data-ttu-id="a4a06-134">다음 XML에서는 구성 기반 발급자 이름 레지스트리를 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a4a06-134">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a4a06-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a4a06-135">See also</span></span>

- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
