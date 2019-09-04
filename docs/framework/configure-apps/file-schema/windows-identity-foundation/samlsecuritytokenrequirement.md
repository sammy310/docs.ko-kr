---
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: cab7572518a7a6dc26f8bbcf67cd424fa1c01085
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251897"
---
# <a name="samlsecuritytokenrequirement"></a><span data-ttu-id="d649a-101">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="d649a-101">\<samlSecurityTokenRequirement></span></span>
<span data-ttu-id="d649a-102"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> 클래스<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> , 클래스 또는 이러한 클래스 중 하나의 파생 클래스에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d649a-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span> <span data-ttu-id="d649a-103"><xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> 클래스로 표현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d649a-103">Represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class.</span></span>  
  
<span data-ttu-id="d649a-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d649a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d649a-105">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="d649a-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="d649a-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="d649a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="d649a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="d649a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="d649a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> 추가**](add.md)</span><span class="sxs-lookup"><span data-stu-id="d649a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="d649a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<samlSecurityTokenRequirement >**</span><span class="sxs-lookup"><span data-stu-id="d649a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<samlSecurityTokenRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d649a-110">구문</span><span class="sxs-lookup"><span data-stu-id="d649a-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d649a-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d649a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d649a-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d649a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d649a-113">특성</span><span class="sxs-lookup"><span data-stu-id="d649a-113">Attributes</span></span>  
  
|<span data-ttu-id="d649a-114">특성</span><span class="sxs-lookup"><span data-stu-id="d649a-114">Attribute</span></span>|<span data-ttu-id="d649a-115">Description</span><span class="sxs-lookup"><span data-stu-id="d649a-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d649a-116">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="d649a-116">mapToWindows</span></span>|<span data-ttu-id="d649a-117">토큰 처리기가 들어오는 UPN 클레임을 사용 하 여 유효성 검사 토큰을 Windows 계정에 매핑할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d649a-117">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="d649a-118">기본값은 "false"입니다.</span><span class="sxs-lookup"><span data-stu-id="d649a-118">The default is "false".</span></span>|  
|<span data-ttu-id="d649a-119">issuerCertificateRevocationMode</span><span class="sxs-lookup"><span data-stu-id="d649a-119">issuerCertificateRevocationMode</span></span>|<span data-ttu-id="d649a-120">X.509 인증서에 사용할 해지 모드를 지정 하는 값입니다.<xref:System.Security.Cryptography.X509Certificates.X509RevocationMode></span><span class="sxs-lookup"><span data-stu-id="d649a-120">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="d649a-121">기본값은 "Online"입니다.</span><span class="sxs-lookup"><span data-stu-id="d649a-121">The default value is "Online".</span></span>|  
|<span data-ttu-id="d649a-122">issuerCertificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="d649a-122">issuerCertificateValidationMode</span></span>|<span data-ttu-id="d649a-123">X.509 인증서에 사용할 유효성 검사 모드를 지정 하는 값입니다.<xref:System.ServiceModel.Security.X509CertificateValidationMode></span><span class="sxs-lookup"><span data-stu-id="d649a-123">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="d649a-124">기본값은 "PeerOrChainTrust"입니다.</span><span class="sxs-lookup"><span data-stu-id="d649a-124">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="d649a-125">issuerCertificateTrustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="d649a-125">issuerCertificateTrustedStoreLocation</span></span>|<span data-ttu-id="d649a-126">X.509 인증서 저장소를 지정 하는 값입니다.<xref:System.Security.Cryptography.X509Certificates.StoreLocation></span><span class="sxs-lookup"><span data-stu-id="d649a-126">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="d649a-127">기본값은 "LocalMachine"입니다.</span><span class="sxs-lookup"><span data-stu-id="d649a-127">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="d649a-128">issuerCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="d649a-128">issuerCertificateValidator</span></span>|<span data-ttu-id="d649a-129">에서 <xref:System.IdentityModel.Selectors.X509CertificateValidator>파생 되는 사용자 지정 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d649a-129">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="d649a-130">`issuerCertificateValidationMode` 특성이 "Custom" 이면 발급자 인증서 유효성 검사에이 형식의 인스턴스가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d649a-130">If the `issuerCertificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d649a-131">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d649a-131">Child Elements</span></span>  
  
|<span data-ttu-id="d649a-132">요소</span><span class="sxs-lookup"><span data-stu-id="d649a-132">Element</span></span>|<span data-ttu-id="d649a-133">Description</span><span class="sxs-lookup"><span data-stu-id="d649a-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d649a-134">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="d649a-134">\<nameClaimType></span></span>](nameclaimtype.md)|<span data-ttu-id="d649a-135">속성을 <xref:System.Security.Principal.IIdentity.Name%2A> 지정 하는 클레임 유형을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d649a-135">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span>|  
|[<span data-ttu-id="d649a-136">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="d649a-136">\<roleClaimType></span></span>](roleclaimtype.md)|<span data-ttu-id="d649a-137">토큰 처리기의 <xref:System.Security.Claims.ClaimsIdentity> <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> 메서드에서 반환 하는 개체의 컬렉션에서 역할 유형 클레임을 정의 하는 클레임 유형을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d649a-137">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d649a-138">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d649a-138">Parent Elements</span></span>  
  
|<span data-ttu-id="d649a-139">요소</span><span class="sxs-lookup"><span data-stu-id="d649a-139">Element</span></span>|<span data-ttu-id="d649a-140">설명</span><span class="sxs-lookup"><span data-stu-id="d649a-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d649a-141">\<add></span><span class="sxs-lookup"><span data-stu-id="d649a-141">\<add></span></span>](add.md)|<span data-ttu-id="d649a-142">지정 된 보안 토큰 처리기를 토큰 처리기 컬렉션에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d649a-142">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d649a-143">설명</span><span class="sxs-lookup"><span data-stu-id="d649a-143">Remarks</span></span>  
 <span data-ttu-id="d649a-144">요소 `<samlSecurityTokenRequirement>` 는 개체 모델에서 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> 클래스로 표시 되며 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> 또는 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>에서 `SamlSecurityTokenRequirement` 속성을 구성 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d649a-144">The `<samlSecurityTokenRequirement>` element is represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class in the object model and is used to configure the `SamlSecurityTokenRequirement` property on a <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> or a <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d649a-145">예제</span><span class="sxs-lookup"><span data-stu-id="d649a-145">Example</span></span>  
  
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
