---
title: <x509SecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: 76eeea635fd65486a1c16bea15a49018876dae99
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251690"
---
# <a name="x509securitytokenhandlerrequirement"></a><span data-ttu-id="0b320-101">\<x509SecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="0b320-101">\<x509SecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="0b320-102"><xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> 클래스 또는 파생 클래스에 대 한 선택적 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b320-102">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
<span data-ttu-id="0b320-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0b320-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0b320-104">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="0b320-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="0b320-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="0b320-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="0b320-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="0b320-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="0b320-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> 추가**](add.md)</span><span class="sxs-lookup"><span data-stu-id="0b320-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="0b320-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<x509SecurityTokenHandlerRequirement >**</span><span class="sxs-lookup"><span data-stu-id="0b320-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<x509SecurityTokenHandlerRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b320-109">구문</span><span class="sxs-lookup"><span data-stu-id="0b320-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
        <x509SecurityTokenHandlerRequirement>  
          mapToWindows=xs:boolean  
          certificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
          certificateValidator="Namespace.Class, Assembly"  
          revocationMode="NoCheck||Offline||Online"  
          trustedStoreLocation="CurrentUser||LocalMachine"  
        </x509SecurityTokenHandlerRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0b320-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0b320-110">Attributes and Elements</span></span>  
 <span data-ttu-id="0b320-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0b320-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0b320-112">특성</span><span class="sxs-lookup"><span data-stu-id="0b320-112">Attributes</span></span>  
  
|<span data-ttu-id="0b320-113">특성</span><span class="sxs-lookup"><span data-stu-id="0b320-113">Attribute</span></span>|<span data-ttu-id="0b320-114">Description</span><span class="sxs-lookup"><span data-stu-id="0b320-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0b320-115">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="0b320-115">certificateValidationMode</span></span>|<span data-ttu-id="0b320-116">X.509 인증서에 사용할 유효성 검사 모드를 지정 하는 값입니다.<xref:System.ServiceModel.Security.X509CertificateValidationMode></span><span class="sxs-lookup"><span data-stu-id="0b320-116">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="0b320-117">기본값은 "PeerOrChainTrust"입니다.</span><span class="sxs-lookup"><span data-stu-id="0b320-117">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="0b320-118">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="0b320-118">mapToWindows</span></span>|<span data-ttu-id="0b320-119">토큰 처리기가 들어오는 UPN 클레임을 사용 하 여 유효성 검사 토큰을 Windows 계정에 매핑할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b320-119">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="0b320-120">기본값은 "false"입니다.</span><span class="sxs-lookup"><span data-stu-id="0b320-120">The default is "false".</span></span>|  
|<span data-ttu-id="0b320-121">revocationMode</span><span class="sxs-lookup"><span data-stu-id="0b320-121">revocationMode</span></span>|<span data-ttu-id="0b320-122">X.509 인증서에 사용할 해지 모드를 지정 하는 값입니다.<xref:System.Security.Cryptography.X509Certificates.X509RevocationMode></span><span class="sxs-lookup"><span data-stu-id="0b320-122">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="0b320-123">기본값은 "Online"입니다.</span><span class="sxs-lookup"><span data-stu-id="0b320-123">The default value is "Online".</span></span>|  
|<span data-ttu-id="0b320-124">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="0b320-124">trustedStoreLocation</span></span>|<span data-ttu-id="0b320-125">X.509 인증서 저장소를 지정 하는 값입니다.<xref:System.Security.Cryptography.X509Certificates.StoreLocation></span><span class="sxs-lookup"><span data-stu-id="0b320-125">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="0b320-126">기본값은 "LocalMachine"입니다.</span><span class="sxs-lookup"><span data-stu-id="0b320-126">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="0b320-127">certificateValidator</span><span class="sxs-lookup"><span data-stu-id="0b320-127">certificateValidator</span></span>|<span data-ttu-id="0b320-128">에서 <xref:System.IdentityModel.Selectors.X509CertificateValidator>파생 되는 사용자 지정 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0b320-128">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="0b320-129">`certificateValidationMode` 특성이 "Custom" 이면 발급자 인증서 유효성 검사에이 형식의 인스턴스가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b320-129">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0b320-130">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0b320-130">Child Elements</span></span>  
 <span data-ttu-id="0b320-131">없음</span><span class="sxs-lookup"><span data-stu-id="0b320-131">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0b320-132">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0b320-132">Parent Elements</span></span>  
  
|<span data-ttu-id="0b320-133">요소</span><span class="sxs-lookup"><span data-stu-id="0b320-133">Element</span></span>|<span data-ttu-id="0b320-134">설명</span><span class="sxs-lookup"><span data-stu-id="0b320-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0b320-135">\<add></span><span class="sxs-lookup"><span data-stu-id="0b320-135">\<add></span></span>](add.md)|<span data-ttu-id="0b320-136">지정 된 보안 토큰 처리기를 토큰 처리기 컬렉션에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b320-136">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0b320-137">예제</span><span class="sxs-lookup"><span data-stu-id="0b320-137">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"   
                                         certificateValidationMode="PeerOrChainTrust"   
                                         revocationMode="Online"   
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
