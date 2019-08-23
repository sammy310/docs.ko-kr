---
title: <x509SecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: 2851820460a34d62175929b48ad57914df557059
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945175"
---
# <a name="x509securitytokenhandlerrequirement"></a><span data-ttu-id="ff52a-101">\<x509SecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="ff52a-101">\<x509SecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="ff52a-102"><xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> 클래스 또는 파생 클래스에 대 한 선택적 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff52a-102">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="ff52a-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="ff52a-103">\<system.identityModel></span></span>  
<span data-ttu-id="ff52a-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="ff52a-104">\<identityConfiguration></span></span>  
<span data-ttu-id="ff52a-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="ff52a-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="ff52a-106">\<add></span><span class="sxs-lookup"><span data-stu-id="ff52a-106">\<add></span></span>  
<span data-ttu-id="ff52a-107">\<x509SecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="ff52a-107">\<x509SecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff52a-108">구문</span><span class="sxs-lookup"><span data-stu-id="ff52a-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ff52a-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ff52a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ff52a-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ff52a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ff52a-111">특성</span><span class="sxs-lookup"><span data-stu-id="ff52a-111">Attributes</span></span>  
  
|<span data-ttu-id="ff52a-112">특성</span><span class="sxs-lookup"><span data-stu-id="ff52a-112">Attribute</span></span>|<span data-ttu-id="ff52a-113">설명</span><span class="sxs-lookup"><span data-stu-id="ff52a-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ff52a-114">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="ff52a-114">certificateValidationMode</span></span>|<span data-ttu-id="ff52a-115">X.509 인증서에 사용할 유효성 검사 모드를 지정 하는 값입니다.<xref:System.ServiceModel.Security.X509CertificateValidationMode></span><span class="sxs-lookup"><span data-stu-id="ff52a-115">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="ff52a-116">기본값은 "PeerOrChainTrust"입니다.</span><span class="sxs-lookup"><span data-stu-id="ff52a-116">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="ff52a-117">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="ff52a-117">mapToWindows</span></span>|<span data-ttu-id="ff52a-118">토큰 처리기가 들어오는 UPN 클레임을 사용 하 여 유효성 검사 토큰을 Windows 계정에 매핑할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff52a-118">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="ff52a-119">기본값은 "false"입니다.</span><span class="sxs-lookup"><span data-stu-id="ff52a-119">The default is "false".</span></span>|  
|<span data-ttu-id="ff52a-120">revocationMode</span><span class="sxs-lookup"><span data-stu-id="ff52a-120">revocationMode</span></span>|<span data-ttu-id="ff52a-121">X.509 인증서에 사용할 해지 모드를 지정 하는 값입니다.<xref:System.Security.Cryptography.X509Certificates.X509RevocationMode></span><span class="sxs-lookup"><span data-stu-id="ff52a-121">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="ff52a-122">기본값은 "Online"입니다.</span><span class="sxs-lookup"><span data-stu-id="ff52a-122">The default value is "Online".</span></span>|  
|<span data-ttu-id="ff52a-123">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="ff52a-123">trustedStoreLocation</span></span>|<span data-ttu-id="ff52a-124">X.509 인증서 저장소를 지정 하는 값입니다.<xref:System.Security.Cryptography.X509Certificates.StoreLocation></span><span class="sxs-lookup"><span data-stu-id="ff52a-124">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="ff52a-125">기본값은 "LocalMachine"입니다.</span><span class="sxs-lookup"><span data-stu-id="ff52a-125">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="ff52a-126">certificateValidator</span><span class="sxs-lookup"><span data-stu-id="ff52a-126">certificateValidator</span></span>|<span data-ttu-id="ff52a-127">에서 <xref:System.IdentityModel.Selectors.X509CertificateValidator>파생 되는 사용자 지정 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ff52a-127">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="ff52a-128">`certificateValidationMode` 특성이 "Custom" 이면 발급자 인증서 유효성 검사에이 형식의 인스턴스가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff52a-128">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ff52a-129">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ff52a-129">Child Elements</span></span>  
 <span data-ttu-id="ff52a-130">없음</span><span class="sxs-lookup"><span data-stu-id="ff52a-130">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ff52a-131">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ff52a-131">Parent Elements</span></span>  
  
|<span data-ttu-id="ff52a-132">요소</span><span class="sxs-lookup"><span data-stu-id="ff52a-132">Element</span></span>|<span data-ttu-id="ff52a-133">설명</span><span class="sxs-lookup"><span data-stu-id="ff52a-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ff52a-134">\<add></span><span class="sxs-lookup"><span data-stu-id="ff52a-134">\<add></span></span>](add.md)|<span data-ttu-id="ff52a-135">지정 된 보안 토큰 처리기를 토큰 처리기 컬렉션에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff52a-135">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ff52a-136">예제</span><span class="sxs-lookup"><span data-stu-id="ff52a-136">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"   
                                         certificateValidationMode="PeerOrChainTrust"   
                                         revocationMode="Online"   
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
