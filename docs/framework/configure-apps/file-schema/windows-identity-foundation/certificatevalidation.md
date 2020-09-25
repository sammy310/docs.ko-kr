---
title: <certificateValidation>
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
ms.openlocfilehash: 583fef7eb364c39890b3f9304770b383c1ea6d2a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183509"
---
# \<certificateValidation>

<span data-ttu-id="dea83-101">토큰 처리기에서 인증서의 유효성을 검사 하는 데 사용 하는 설정을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="dea83-101">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="dea83-102">이러한 설정은 고유한 유효성 검사기를 사용 하 여 특정 처리기를 구성 하는 경우 재정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dea83-102">These settings are overridden if a specific handler is configured with its own validator.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateValidation>**  
  
## <a name="syntax"></a><span data-ttu-id="dea83-103">구문</span><span class="sxs-lookup"><span data-stu-id="dea83-103">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <certificateValidation  
      certificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
      revocationMode="NoCheck||Offline||Online"  
      trustedStoreLocation="CurrentLocation||LocalMachine" >  
    </certificateValidation>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dea83-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="dea83-104">Attributes and Elements</span></span>  

 <span data-ttu-id="dea83-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dea83-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dea83-106">특성</span><span class="sxs-lookup"><span data-stu-id="dea83-106">Attributes</span></span>  
  
|<span data-ttu-id="dea83-107">attribute</span><span class="sxs-lookup"><span data-stu-id="dea83-107">Attribute</span></span>|<span data-ttu-id="dea83-108">설명</span><span class="sxs-lookup"><span data-stu-id="dea83-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dea83-109">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="dea83-109">certificateValidationMode</span></span>|<span data-ttu-id="dea83-110"><xref:System.ServiceModel.Security.X509CertificateValidationMode>X.509 인증서에 사용할 유효성 검사 모드를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="dea83-110">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="dea83-111">기본값은 "PeerOrChainTrust"입니다.</span><span class="sxs-lookup"><span data-stu-id="dea83-111">The default value is "PeerOrChainTrust".</span></span> <span data-ttu-id="dea83-112">사용자 지정 유효성 검사기를 지정 하려면이 특성을 "Custom"으로 설정 하 고 요소를 사용 하 여 유효성 검사기를 지정 합니다 [\<certificateValidator>](certificatevalidator.md) .</span><span class="sxs-lookup"><span data-stu-id="dea83-112">To specify a custom validator, set this attribute to "Custom" and specify the validator using the [\<certificateValidator>](certificatevalidator.md) element.</span></span> <span data-ttu-id="dea83-113">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="dea83-113">Optional.</span></span>|  
|<span data-ttu-id="dea83-114">revocationMode</span><span class="sxs-lookup"><span data-stu-id="dea83-114">revocationMode</span></span>|<span data-ttu-id="dea83-115"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>X.509 인증서에 사용할 해지 모드를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="dea83-115">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="dea83-116">기본값은 "Online"입니다.</span><span class="sxs-lookup"><span data-stu-id="dea83-116">The default value is "Online".</span></span> <span data-ttu-id="dea83-117">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="dea83-117">Optional.</span></span>|  
|<span data-ttu-id="dea83-118">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="dea83-118">trustedStoreLocation</span></span>|<span data-ttu-id="dea83-119"><xref:System.Security.Cryptography.X509Certificates.StoreLocation>X.509 인증서 저장소를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="dea83-119">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="dea83-120">기본값은 "LocalMachine"입니다.</span><span class="sxs-lookup"><span data-stu-id="dea83-120">The default value is "LocalMachine".</span></span> <span data-ttu-id="dea83-121">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="dea83-121">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dea83-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="dea83-122">Child Elements</span></span>  
  
|<span data-ttu-id="dea83-123">요소</span><span class="sxs-lookup"><span data-stu-id="dea83-123">Element</span></span>|<span data-ttu-id="dea83-124">설명</span><span class="sxs-lookup"><span data-stu-id="dea83-124">Description</span></span>|  
|-------------|-----------------|  
|[\<certificateValidator>](certificatevalidator.md)|<span data-ttu-id="dea83-125">인증서 유효성 검사에 대 한 사용자 지정 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dea83-125">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="dea83-126">이 형식은 `certificateValidationMode` [\<certificateValidation>](certificatevalidation.md) 요소의 특성이 "Custom"으로 설정 된 경우에만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dea83-126">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dea83-127">부모 요소</span><span class="sxs-lookup"><span data-stu-id="dea83-127">Parent Elements</span></span>  
  
|<span data-ttu-id="dea83-128">요소</span><span class="sxs-lookup"><span data-stu-id="dea83-128">Element</span></span>|<span data-ttu-id="dea83-129">설명</span><span class="sxs-lookup"><span data-stu-id="dea83-129">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="dea83-130">서비스 수준 id 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dea83-130">Specifies service-level identity settings.</span></span>|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="dea83-131">보안 토큰 처리기의 컬렉션에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dea83-131">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dea83-132">설명</span><span class="sxs-lookup"><span data-stu-id="dea83-132">Remarks</span></span>  

 <span data-ttu-id="dea83-133">요소는 요소 아래의 `<certificateValidation>` 서비스 수준 `<identityConfiguration>` 또는 요소의 보안 토큰 처리기 컬렉션 수준에서 지정할 수 있습니다 `<securityTokenHandlerConfiguration>` .</span><span class="sxs-lookup"><span data-stu-id="dea83-133">A `<certificateValidation>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="dea83-134">토큰 처리기 컬렉션의 설정은 서비스에 지정 된 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="dea83-134">Settings on a token handler collection override those specified on the service.</span></span> <span data-ttu-id="dea83-135">일부 토큰 처리기를 사용 하면 구성에서 인증서 유효성 검사 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dea83-135">Some token handlers allow you to specify certificate validation settings in configuration.</span></span> <span data-ttu-id="dea83-136">개별 토큰 처리기의 설정은 서비스 수준 및 보안 토큰 처리기 컬렉션 둘 다에서 지정 된 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="dea83-136">Settings on individual token handlers override those specified both at the service level and on the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dea83-137">예제</span><span class="sxs-lookup"><span data-stu-id="dea83-137">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```
