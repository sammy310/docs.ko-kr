---
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: e1b8acd48ee185b3c6c50f70321bb9ca66e8e02b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793863"
---
# <a name="samlsecuritytokenrequirement"></a><span data-ttu-id="c611d-101">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="c611d-101">\<samlSecurityTokenRequirement></span></span>
<span data-ttu-id="c611d-102">에 대 한 구성을 제공 합니다 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> 클래스는 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 클래스나 파생된 클래스의 이러한 클래스 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="c611d-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span> <span data-ttu-id="c611d-103">표시 된 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="c611d-103">Represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class.</span></span>  
  
 <span data-ttu-id="c611d-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="c611d-104">\<system.identityModel></span></span>  
<span data-ttu-id="c611d-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="c611d-105">\<identityConfiguration></span></span>  
<span data-ttu-id="c611d-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="c611d-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="c611d-107">\<add></span><span class="sxs-lookup"><span data-stu-id="c611d-107">\<add></span></span>  
<span data-ttu-id="c611d-108">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="c611d-108">\<samlSecurityTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c611d-109">구문</span><span class="sxs-lookup"><span data-stu-id="c611d-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c611d-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c611d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c611d-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c611d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c611d-112">특성</span><span class="sxs-lookup"><span data-stu-id="c611d-112">Attributes</span></span>  
  
|<span data-ttu-id="c611d-113">특성</span><span class="sxs-lookup"><span data-stu-id="c611d-113">Attribute</span></span>|<span data-ttu-id="c611d-114">설명</span><span class="sxs-lookup"><span data-stu-id="c611d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c611d-115">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="c611d-115">mapToWindows</span></span>|<span data-ttu-id="c611d-116">여부를 토큰 처리기를 매핑해야 유효성 검사 토큰이 Windows 계정에 들어오는 UPN 클레임을 사용 하 여 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c611d-116">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="c611d-117">기본값은 "false"입니다.</span><span class="sxs-lookup"><span data-stu-id="c611d-117">The default is "false".</span></span>|  
|<span data-ttu-id="c611d-118">issuerCertificateRevocationMode</span><span class="sxs-lookup"><span data-stu-id="c611d-118">issuerCertificateRevocationMode</span></span>|<span data-ttu-id="c611d-119"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> 사용할 X.509 인증서의 해지 모드를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c611d-119">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="c611d-120">기본값은 "Online"입니다.</span><span class="sxs-lookup"><span data-stu-id="c611d-120">The default value is "Online".</span></span>|  
|<span data-ttu-id="c611d-121">issuerCertificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="c611d-121">issuerCertificateValidationMode</span></span>|<span data-ttu-id="c611d-122"><xref:System.ServiceModel.Security.X509CertificateValidationMode> 사용할 X.509 인증서의 유효성 검사 모드를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c611d-122">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="c611d-123">기본값은 "PeerOrChainTrust"입니다.</span><span class="sxs-lookup"><span data-stu-id="c611d-123">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="c611d-124">issuerCertificateTrustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="c611d-124">issuerCertificateTrustedStoreLocation</span></span>|<span data-ttu-id="c611d-125"><xref:System.Security.Cryptography.X509Certificates.StoreLocation> X.509 인증서 저장소를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c611d-125">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="c611d-126">기본값은 "LocalMachine"입니다.</span><span class="sxs-lookup"><span data-stu-id="c611d-126">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="c611d-127">issuerCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="c611d-127">issuerCertificateValidator</span></span>|<span data-ttu-id="c611d-128">파생 되는 사용자 지정 형식을 <xref:System.IdentityModel.Selectors.X509CertificateValidator>합니다.</span><span class="sxs-lookup"><span data-stu-id="c611d-128">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="c611d-129">경우는 `issuerCertificateValidationMode` 특성은 "Custom"을이 형식의 인스턴스는 발급자 인증서 유효성 검사에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c611d-129">If the `issuerCertificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c611d-130">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c611d-130">Child Elements</span></span>  
  
|<span data-ttu-id="c611d-131">요소</span><span class="sxs-lookup"><span data-stu-id="c611d-131">Element</span></span>|<span data-ttu-id="c611d-132">설명</span><span class="sxs-lookup"><span data-stu-id="c611d-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c611d-133">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="c611d-133">\<nameClaimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/nameclaimtype.md)|<span data-ttu-id="c611d-134">지정 하는 클레임 형식을 가져오거나 설정 합니다 <xref:System.Security.Principal.IIdentity.Name%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="c611d-134">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span>|  
|[<span data-ttu-id="c611d-135">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="c611d-135">\<roleClaimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/roleclaimtype.md)|<span data-ttu-id="c611d-136">컬렉션의 역할 유형 클레임을 정의 하는 클레임 유형을 <xref:System.Security.Claims.ClaimsIdentity> 반환한 개체는 <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> 토큰 처리기의 메서드.</span><span class="sxs-lookup"><span data-stu-id="c611d-136">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c611d-137">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c611d-137">Parent Elements</span></span>  
  
|<span data-ttu-id="c611d-138">요소</span><span class="sxs-lookup"><span data-stu-id="c611d-138">Element</span></span>|<span data-ttu-id="c611d-139">설명</span><span class="sxs-lookup"><span data-stu-id="c611d-139">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c611d-140">\<add></span><span class="sxs-lookup"><span data-stu-id="c611d-140">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="c611d-141">토큰 처리기 컬렉션에 지정 된 보안 토큰 처리기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c611d-141">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c611d-142">설명</span><span class="sxs-lookup"><span data-stu-id="c611d-142">Remarks</span></span>  
 <span data-ttu-id="c611d-143">`<samlSecurityTokenRequirement>` 요소에서 표현 됩니다는 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> 개체 모델에서 클래스 및 구성 하는 데 사용 되는 `SamlSecurityTokenRequirement` 속성을 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> 또는 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span><span class="sxs-lookup"><span data-stu-id="c611d-143">The `<samlSecurityTokenRequirement>` element is represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class in the object model and is used to configure the `SamlSecurityTokenRequirement` property on a <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> or a <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c611d-144">예제</span><span class="sxs-lookup"><span data-stu-id="c611d-144">Example</span></span>  
  
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
