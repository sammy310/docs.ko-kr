---
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: b27f337189a7d0b66ffd38e032b5eb864e5094a1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152634"
---
# \<samlSecurityTokenRequirement>
<span data-ttu-id="1020f-101"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>클래스, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 클래스 또는 이러한 클래스 중 하나의 파생 클래스에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1020f-101">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span> <span data-ttu-id="1020f-102"><xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>클래스로 표현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1020f-102">Represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<samlSecurityTokenRequirement>**  
  
## <a name="syntax"></a><span data-ttu-id="1020f-103">구문</span><span class="sxs-lookup"><span data-stu-id="1020f-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1020f-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1020f-104">Attributes and Elements</span></span>  
 <span data-ttu-id="1020f-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1020f-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1020f-106">특성</span><span class="sxs-lookup"><span data-stu-id="1020f-106">Attributes</span></span>  
  
|<span data-ttu-id="1020f-107">attribute</span><span class="sxs-lookup"><span data-stu-id="1020f-107">Attribute</span></span>|<span data-ttu-id="1020f-108">Description</span><span class="sxs-lookup"><span data-stu-id="1020f-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1020f-109">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="1020f-109">mapToWindows</span></span>|<span data-ttu-id="1020f-110">토큰 처리기가 들어오는 UPN 클레임을 사용 하 여 유효성 검사 토큰을 Windows 계정에 매핑할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1020f-110">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="1020f-111">기본값은 "false"입니다.</span><span class="sxs-lookup"><span data-stu-id="1020f-111">The default is "false".</span></span>|  
|<span data-ttu-id="1020f-112">issuerCertificateRevocationMode</span><span class="sxs-lookup"><span data-stu-id="1020f-112">issuerCertificateRevocationMode</span></span>|<span data-ttu-id="1020f-113"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>X.509 인증서에 사용할 해지 모드를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1020f-113">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="1020f-114">기본값은 "Online"입니다.</span><span class="sxs-lookup"><span data-stu-id="1020f-114">The default value is "Online".</span></span>|  
|<span data-ttu-id="1020f-115">issuerCertificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="1020f-115">issuerCertificateValidationMode</span></span>|<span data-ttu-id="1020f-116"><xref:System.ServiceModel.Security.X509CertificateValidationMode>X.509 인증서에 사용할 유효성 검사 모드를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1020f-116">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="1020f-117">기본값은 "PeerOrChainTrust"입니다.</span><span class="sxs-lookup"><span data-stu-id="1020f-117">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="1020f-118">issuerCertificateTrustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="1020f-118">issuerCertificateTrustedStoreLocation</span></span>|<span data-ttu-id="1020f-119"><xref:System.Security.Cryptography.X509Certificates.StoreLocation>X.509 인증서 저장소를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1020f-119">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="1020f-120">기본값은 "LocalMachine"입니다.</span><span class="sxs-lookup"><span data-stu-id="1020f-120">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="1020f-121">issuerCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="1020f-121">issuerCertificateValidator</span></span>|<span data-ttu-id="1020f-122">에서 파생 되는 사용자 지정 형식 <xref:System.IdentityModel.Selectors.X509CertificateValidator> 입니다.</span><span class="sxs-lookup"><span data-stu-id="1020f-122">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="1020f-123">`issuerCertificateValidationMode`특성이 "Custom" 이면 발급자 인증서 유효성 검사에이 형식의 인스턴스가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1020f-123">If the `issuerCertificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1020f-124">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1020f-124">Child Elements</span></span>  
  
|<span data-ttu-id="1020f-125">요소</span><span class="sxs-lookup"><span data-stu-id="1020f-125">Element</span></span>|<span data-ttu-id="1020f-126">Description</span><span class="sxs-lookup"><span data-stu-id="1020f-126">Description</span></span>|  
|-------------|-----------------|  
|[\<nameClaimType>](nameclaimtype.md)|<span data-ttu-id="1020f-127">속성을 지정 하는 클레임 유형을 설정 합니다 <xref:System.Security.Principal.IIdentity.Name%2A> .</span><span class="sxs-lookup"><span data-stu-id="1020f-127">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span>|  
|[\<roleClaimType>](roleclaimtype.md)|<span data-ttu-id="1020f-128"><xref:System.Security.Claims.ClaimsIdentity>토큰 처리기의 메서드에서 반환 하는 개체의 컬렉션에서 역할 유형 클레임을 정의 하는 클레임 유형을 지정 합니다 <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> .</span><span class="sxs-lookup"><span data-stu-id="1020f-128">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1020f-129">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1020f-129">Parent Elements</span></span>  
  
|<span data-ttu-id="1020f-130">요소</span><span class="sxs-lookup"><span data-stu-id="1020f-130">Element</span></span>|<span data-ttu-id="1020f-131">Description</span><span class="sxs-lookup"><span data-stu-id="1020f-131">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add.md)|<span data-ttu-id="1020f-132">지정 된 보안 토큰 처리기를 토큰 처리기 컬렉션에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1020f-132">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1020f-133">설명</span><span class="sxs-lookup"><span data-stu-id="1020f-133">Remarks</span></span>  
 <span data-ttu-id="1020f-134">`<samlSecurityTokenRequirement>`요소는 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> 개체 모델에서 클래스로 표시 되며 `SamlSecurityTokenRequirement` 또는에서 속성을 구성 하는 데 사용 됩니다 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> .</span><span class="sxs-lookup"><span data-stu-id="1020f-134">The `<samlSecurityTokenRequirement>` element is represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class in the object model and is used to configure the `SamlSecurityTokenRequirement` property on a <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> or a <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1020f-135">예제</span><span class="sxs-lookup"><span data-stu-id="1020f-135">Example</span></span>  
  
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
