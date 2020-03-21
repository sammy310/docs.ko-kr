---
title: <x509SecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: 30ce69a35cfdd34e0dfea5c682347eb9187e04ed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152452"
---
# <a name="x509securitytokenhandlerrequirement"></a><span data-ttu-id="e9be2-101">\<x509보안토큰처리기></span><span class="sxs-lookup"><span data-stu-id="e9be2-101">\<x509SecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="e9be2-102">클래스 또는 파생 <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> 클래스에 대한 선택적 구성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e9be2-102">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
<span data-ttu-id="e9be2-103">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e9be2-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e9be2-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="e9be2-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="e9be2-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<ID구성>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="e9be2-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="e9be2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<보안토큰처리기>**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="e9be2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="e9be2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>추가**](add.md)</span><span class="sxs-lookup"><span data-stu-id="e9be2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="e9be2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<x509보안토큰처리기>**</span><span class="sxs-lookup"><span data-stu-id="e9be2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<x509SecurityTokenHandlerRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9be2-109">구문</span><span class="sxs-lookup"><span data-stu-id="e9be2-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9be2-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e9be2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e9be2-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e9be2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9be2-112">특성</span><span class="sxs-lookup"><span data-stu-id="e9be2-112">Attributes</span></span>  
  
|<span data-ttu-id="e9be2-113">attribute</span><span class="sxs-lookup"><span data-stu-id="e9be2-113">Attribute</span></span>|<span data-ttu-id="e9be2-114">Description</span><span class="sxs-lookup"><span data-stu-id="e9be2-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e9be2-115">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="e9be2-115">certificateValidationMode</span></span>|<span data-ttu-id="e9be2-116">X.509 인증서에 사용할 유효성 검사 모드를 지정하는 <xref:System.ServiceModel.Security.X509CertificateValidationMode> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e9be2-116">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="e9be2-117">기본값은 "피어로체인트러스트"입니다.</span><span class="sxs-lookup"><span data-stu-id="e9be2-117">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="e9be2-118">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="e9be2-118">mapToWindows</span></span>|<span data-ttu-id="e9be2-119">들어오는 UPN 클레임을 사용하여 토큰 처리기가 유효성 검사 토큰을 Windows 계정에 매핑할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e9be2-119">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="e9be2-120">기본값은 "false"입니다.</span><span class="sxs-lookup"><span data-stu-id="e9be2-120">The default is "false".</span></span>|  
|<span data-ttu-id="e9be2-121">revocationMode</span><span class="sxs-lookup"><span data-stu-id="e9be2-121">revocationMode</span></span>|<span data-ttu-id="e9be2-122">X.509 인증서에 사용할 해지 모드를 지정하는 <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e9be2-122">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="e9be2-123">기본값은 "온라인"입니다.</span><span class="sxs-lookup"><span data-stu-id="e9be2-123">The default value is "Online".</span></span>|  
|<span data-ttu-id="e9be2-124">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="e9be2-124">trustedStoreLocation</span></span>|<span data-ttu-id="e9be2-125">X.509 인증서 저장소를 지정하는 <xref:System.Security.Cryptography.X509Certificates.StoreLocation> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e9be2-125">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="e9be2-126">기본값은 "로컬Machine"입니다.</span><span class="sxs-lookup"><span data-stu-id="e9be2-126">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="e9be2-127">인증서유효성 검사자</span><span class="sxs-lookup"><span data-stu-id="e9be2-127">certificateValidator</span></span>|<span data-ttu-id="e9be2-128">에서 파생되는 사용자 <xref:System.IdentityModel.Selectors.X509CertificateValidator>지정 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e9be2-128">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="e9be2-129">특성이 `certificateValidationMode` "사용자 지정"인 경우 이 유형의 인스턴스가 발급자 인증서 유효성 검사에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9be2-129">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e9be2-130">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e9be2-130">Child Elements</span></span>  
 <span data-ttu-id="e9be2-131">None</span><span class="sxs-lookup"><span data-stu-id="e9be2-131">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e9be2-132">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e9be2-132">Parent Elements</span></span>  
  
|<span data-ttu-id="e9be2-133">요소</span><span class="sxs-lookup"><span data-stu-id="e9be2-133">Element</span></span>|<span data-ttu-id="e9be2-134">Description</span><span class="sxs-lookup"><span data-stu-id="e9be2-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e9be2-135">\<>추가</span><span class="sxs-lookup"><span data-stu-id="e9be2-135">\<add></span></span>](add.md)|<span data-ttu-id="e9be2-136">지정된 보안 토큰 처리기를 토큰 처리기 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e9be2-136">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e9be2-137">예제</span><span class="sxs-lookup"><span data-stu-id="e9be2-137">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"
                                         certificateValidationMode="PeerOrChainTrust"
                                         revocationMode="Online"
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
