---
title: <x509SecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: a6a8185297e1345de9fa20c7d4d0dffbdcd8620f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185394"
---
# \<x509SecurityTokenHandlerRequirement>

<span data-ttu-id="1d1b0-101">클래스 또는 파생 클래스에 대 한 선택적 구성을 제공 <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1b0-101">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<x509SecurityTokenHandlerRequirement>**  
  
## <a name="syntax"></a><span data-ttu-id="1d1b0-102">구문</span><span class="sxs-lookup"><span data-stu-id="1d1b0-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1d1b0-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1d1b0-103">Attributes and Elements</span></span>  

 <span data-ttu-id="1d1b0-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1b0-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1d1b0-105">특성</span><span class="sxs-lookup"><span data-stu-id="1d1b0-105">Attributes</span></span>  
  
|<span data-ttu-id="1d1b0-106">attribute</span><span class="sxs-lookup"><span data-stu-id="1d1b0-106">Attribute</span></span>|<span data-ttu-id="1d1b0-107">설명</span><span class="sxs-lookup"><span data-stu-id="1d1b0-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1d1b0-108">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="1d1b0-108">certificateValidationMode</span></span>|<span data-ttu-id="1d1b0-109"><xref:System.ServiceModel.Security.X509CertificateValidationMode>X.509 인증서에 사용할 유효성 검사 모드를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1d1b0-109">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="1d1b0-110">기본값은 "PeerOrChainTrust"입니다.</span><span class="sxs-lookup"><span data-stu-id="1d1b0-110">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="1d1b0-111">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="1d1b0-111">mapToWindows</span></span>|<span data-ttu-id="1d1b0-112">토큰 처리기가 들어오는 UPN 클레임을 사용 하 여 유효성 검사 토큰을 Windows 계정에 매핑할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1b0-112">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="1d1b0-113">기본값은 "false"입니다.</span><span class="sxs-lookup"><span data-stu-id="1d1b0-113">The default is "false".</span></span>|  
|<span data-ttu-id="1d1b0-114">revocationMode</span><span class="sxs-lookup"><span data-stu-id="1d1b0-114">revocationMode</span></span>|<span data-ttu-id="1d1b0-115"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>X.509 인증서에 사용할 해지 모드를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1d1b0-115">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="1d1b0-116">기본값은 "Online"입니다.</span><span class="sxs-lookup"><span data-stu-id="1d1b0-116">The default value is "Online".</span></span>|  
|<span data-ttu-id="1d1b0-117">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="1d1b0-117">trustedStoreLocation</span></span>|<span data-ttu-id="1d1b0-118"><xref:System.Security.Cryptography.X509Certificates.StoreLocation>X.509 인증서 저장소를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1d1b0-118">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="1d1b0-119">기본값은 "LocalMachine"입니다.</span><span class="sxs-lookup"><span data-stu-id="1d1b0-119">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="1d1b0-120">certificateValidator</span><span class="sxs-lookup"><span data-stu-id="1d1b0-120">certificateValidator</span></span>|<span data-ttu-id="1d1b0-121">에서 파생 되는 사용자 지정 형식 <xref:System.IdentityModel.Selectors.X509CertificateValidator> 입니다.</span><span class="sxs-lookup"><span data-stu-id="1d1b0-121">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="1d1b0-122">`certificateValidationMode`특성이 "Custom" 이면 발급자 인증서 유효성 검사에이 형식의 인스턴스가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d1b0-122">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1d1b0-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1d1b0-123">Child Elements</span></span>  

 <span data-ttu-id="1d1b0-124">없음</span><span class="sxs-lookup"><span data-stu-id="1d1b0-124">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1d1b0-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1d1b0-125">Parent Elements</span></span>  
  
|<span data-ttu-id="1d1b0-126">요소</span><span class="sxs-lookup"><span data-stu-id="1d1b0-126">Element</span></span>|<span data-ttu-id="1d1b0-127">설명</span><span class="sxs-lookup"><span data-stu-id="1d1b0-127">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add.md)|<span data-ttu-id="1d1b0-128">지정 된 보안 토큰 처리기를 토큰 처리기 컬렉션에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1b0-128">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1d1b0-129">예제</span><span class="sxs-lookup"><span data-stu-id="1d1b0-129">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"
                                         certificateValidationMode="PeerOrChainTrust"
                                         revocationMode="Online"
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
