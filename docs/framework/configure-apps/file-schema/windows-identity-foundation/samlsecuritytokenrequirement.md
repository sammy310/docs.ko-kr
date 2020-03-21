---
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: b27f337189a7d0b66ffd38e032b5eb864e5094a1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152634"
---
# <a name="samlsecuritytokenrequirement"></a><span data-ttu-id="f1c41-101">\<samlSecurity토큰요구 사항></span><span class="sxs-lookup"><span data-stu-id="f1c41-101">\<samlSecurityTokenRequirement></span></span>
<span data-ttu-id="f1c41-102">이러한 클래스 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> 중 하나의 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 클래스, 클래스 또는 파생 클래스에 대한 구성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c41-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span> <span data-ttu-id="f1c41-103">클래스로 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1c41-103">Represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class.</span></span>  
  
<span data-ttu-id="f1c41-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f1c41-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f1c41-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="f1c41-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="f1c41-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<ID구성>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="f1c41-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="f1c41-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<보안토큰처리기>**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="f1c41-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="f1c41-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>추가**](add.md)</span><span class="sxs-lookup"><span data-stu-id="f1c41-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="f1c41-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<samlSecurity토큰>**</span><span class="sxs-lookup"><span data-stu-id="f1c41-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<samlSecurityTokenRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1c41-110">구문</span><span class="sxs-lookup"><span data-stu-id="f1c41-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement
            issuerCertificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
            issuerCertificateRevocationMode="NoCheck||Offline||Online"  
            issuerCertificateTrustedStoreLocation="CurrentLocation||LocalMachine"  
            issuerCertificateValidator="Namespace.Class Assembly"  
            mapToWindows=xs:boolean  
          <nameClaimType value=xs:string />  
          <roleClaimType value=xs:string />  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f1c41-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f1c41-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f1c41-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c41-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f1c41-113">특성</span><span class="sxs-lookup"><span data-stu-id="f1c41-113">Attributes</span></span>  
  
|<span data-ttu-id="f1c41-114">attribute</span><span class="sxs-lookup"><span data-stu-id="f1c41-114">Attribute</span></span>|<span data-ttu-id="f1c41-115">Description</span><span class="sxs-lookup"><span data-stu-id="f1c41-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f1c41-116">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="f1c41-116">mapToWindows</span></span>|<span data-ttu-id="f1c41-117">들어오는 UPN 클레임을 사용하여 토큰 처리기가 유효성 검사 토큰을 Windows 계정에 매핑할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c41-117">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="f1c41-118">기본값은 "false"입니다.</span><span class="sxs-lookup"><span data-stu-id="f1c41-118">The default is "false".</span></span>|  
|<span data-ttu-id="f1c41-119">발급자인증서 갱신 모드</span><span class="sxs-lookup"><span data-stu-id="f1c41-119">issuerCertificateRevocationMode</span></span>|<span data-ttu-id="f1c41-120">X.509 인증서에 사용할 해지 모드를 지정하는 <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f1c41-120">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="f1c41-121">기본값은 "온라인"입니다.</span><span class="sxs-lookup"><span data-stu-id="f1c41-121">The default value is "Online".</span></span>|  
|<span data-ttu-id="f1c41-122">발급자인증서유효성 검사모드</span><span class="sxs-lookup"><span data-stu-id="f1c41-122">issuerCertificateValidationMode</span></span>|<span data-ttu-id="f1c41-123">X.509 인증서에 사용할 유효성 검사 모드를 지정하는 <xref:System.ServiceModel.Security.X509CertificateValidationMode> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f1c41-123">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="f1c41-124">기본값은 "피어로체인트러스트"입니다.</span><span class="sxs-lookup"><span data-stu-id="f1c41-124">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="f1c41-125">발급자인증서신뢰할 수 있는 스토어위치</span><span class="sxs-lookup"><span data-stu-id="f1c41-125">issuerCertificateTrustedStoreLocation</span></span>|<span data-ttu-id="f1c41-126">X.509 인증서 저장소를 지정하는 <xref:System.Security.Cryptography.X509Certificates.StoreLocation> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f1c41-126">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="f1c41-127">기본값은 "로컬Machine"입니다.</span><span class="sxs-lookup"><span data-stu-id="f1c41-127">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="f1c41-128">발행자인증서유효성 검사자</span><span class="sxs-lookup"><span data-stu-id="f1c41-128">issuerCertificateValidator</span></span>|<span data-ttu-id="f1c41-129">에서 파생되는 사용자 <xref:System.IdentityModel.Selectors.X509CertificateValidator>지정 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f1c41-129">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="f1c41-130">특성이 `issuerCertificateValidationMode` "사용자 지정"인 경우 이 유형의 인스턴스가 발급자 인증서 유효성 검사에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1c41-130">If the `issuerCertificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f1c41-131">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f1c41-131">Child Elements</span></span>  
  
|<span data-ttu-id="f1c41-132">요소</span><span class="sxs-lookup"><span data-stu-id="f1c41-132">Element</span></span>|<span data-ttu-id="f1c41-133">Description</span><span class="sxs-lookup"><span data-stu-id="f1c41-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f1c41-134">\<이름 클레임 유형></span><span class="sxs-lookup"><span data-stu-id="f1c41-134">\<nameClaimType></span></span>](nameclaimtype.md)|<span data-ttu-id="f1c41-135">속성을 지정하는 클레임 유형을 <xref:System.Security.Principal.IIdentity.Name%2A> 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c41-135">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span>|  
|[<span data-ttu-id="f1c41-136">\<역할 클레임 유형></span><span class="sxs-lookup"><span data-stu-id="f1c41-136">\<roleClaimType></span></span>](roleclaimtype.md)|<span data-ttu-id="f1c41-137">토큰 처리기의 <xref:System.Security.Claims.ClaimsIdentity> <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> 메서드에 의해 반환 되는 개체컬렉션에서 역할 형식 클레임을 정의 하는 클레임 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c41-137">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f1c41-138">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f1c41-138">Parent Elements</span></span>  
  
|<span data-ttu-id="f1c41-139">요소</span><span class="sxs-lookup"><span data-stu-id="f1c41-139">Element</span></span>|<span data-ttu-id="f1c41-140">Description</span><span class="sxs-lookup"><span data-stu-id="f1c41-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f1c41-141">\<>추가</span><span class="sxs-lookup"><span data-stu-id="f1c41-141">\<add></span></span>](add.md)|<span data-ttu-id="f1c41-142">지정된 보안 토큰 처리기를 토큰 처리기 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c41-142">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1c41-143">설명</span><span class="sxs-lookup"><span data-stu-id="f1c41-143">Remarks</span></span>  
 <span data-ttu-id="f1c41-144">`<samlSecurityTokenRequirement>` 요소는 개체 모델의 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> 클래스로 표시되며 또는 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>에서 `SamlSecurityTokenRequirement` 속성을 구성하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1c41-144">The `<samlSecurityTokenRequirement>` element is represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class in the object model and is used to configure the `SamlSecurityTokenRequirement` property on a <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> or a <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1c41-145">예제</span><span class="sxs-lookup"><span data-stu-id="f1c41-145">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement issuerCertificateValidationMode="PeerOrChainTrust"  
                                  issuerCertificateRevocationMode="Online"  
                                  issuerCertificateTrustedStoreLocation="LocalMachine"  
                                  mapToWindows="false">  
  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```
