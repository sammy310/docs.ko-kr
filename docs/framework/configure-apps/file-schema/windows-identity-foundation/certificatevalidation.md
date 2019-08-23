---
title: <certificateValidation>
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
ms.openlocfilehash: 8185153eb02c5794b0f6ac02a6837806f2073c07
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941914"
---
# <a name="certificatevalidation"></a><span data-ttu-id="6461d-101">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="6461d-101">\<certificateValidation></span></span>
<span data-ttu-id="6461d-102">토큰 처리기에서 인증서의 유효성을 검사 하는 데 사용 하는 설정을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="6461d-102">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="6461d-103">이러한 설정은 고유한 유효성 검사기를 사용 하 여 특정 처리기를 구성 하는 경우 재정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6461d-103">These settings are overridden if a specific handler is configured with its own validator.</span></span>  
  
 <span data-ttu-id="6461d-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="6461d-104">\<system.identityModel></span></span>  
<span data-ttu-id="6461d-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="6461d-105">\<identityConfiguration></span></span>  
<span data-ttu-id="6461d-106">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="6461d-106">\<certificateValidation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6461d-107">구문</span><span class="sxs-lookup"><span data-stu-id="6461d-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6461d-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="6461d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6461d-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6461d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6461d-110">특성</span><span class="sxs-lookup"><span data-stu-id="6461d-110">Attributes</span></span>  
  
|<span data-ttu-id="6461d-111">특성</span><span class="sxs-lookup"><span data-stu-id="6461d-111">Attribute</span></span>|<span data-ttu-id="6461d-112">Description</span><span class="sxs-lookup"><span data-stu-id="6461d-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6461d-113">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="6461d-113">certificateValidationMode</span></span>|<span data-ttu-id="6461d-114">X.509 인증서에 사용할 유효성 검사 모드를 지정 하는 값입니다.<xref:System.ServiceModel.Security.X509CertificateValidationMode></span><span class="sxs-lookup"><span data-stu-id="6461d-114">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="6461d-115">기본값은 "PeerOrChainTrust"입니다.</span><span class="sxs-lookup"><span data-stu-id="6461d-115">The default value is "PeerOrChainTrust".</span></span> <span data-ttu-id="6461d-116">사용자 지정 유효성 검사기를 지정 하려면이 특성을 "custom"으로 설정 하 고 [ \<certificateValidator >](certificatevalidator.md) 요소를 사용 하 여 유효성 검사기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6461d-116">To specify a custom validator, set this attribute to "Custom" and specify the validator using the [\<certificateValidator>](certificatevalidator.md) element.</span></span> <span data-ttu-id="6461d-117">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="6461d-117">Optional.</span></span>|  
|<span data-ttu-id="6461d-118">revocationMode</span><span class="sxs-lookup"><span data-stu-id="6461d-118">revocationMode</span></span>|<span data-ttu-id="6461d-119">X.509 인증서에 사용할 해지 모드를 지정 하는 값입니다.<xref:System.Security.Cryptography.X509Certificates.X509RevocationMode></span><span class="sxs-lookup"><span data-stu-id="6461d-119">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="6461d-120">기본값은 "Online"입니다.</span><span class="sxs-lookup"><span data-stu-id="6461d-120">The default value is "Online".</span></span> <span data-ttu-id="6461d-121">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="6461d-121">Optional.</span></span>|  
|<span data-ttu-id="6461d-122">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="6461d-122">trustedStoreLocation</span></span>|<span data-ttu-id="6461d-123">X.509 인증서 저장소를 지정 하는 값입니다.<xref:System.Security.Cryptography.X509Certificates.StoreLocation></span><span class="sxs-lookup"><span data-stu-id="6461d-123">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="6461d-124">기본값은 "LocalMachine"입니다.</span><span class="sxs-lookup"><span data-stu-id="6461d-124">The default value is "LocalMachine".</span></span> <span data-ttu-id="6461d-125">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="6461d-125">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6461d-126">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6461d-126">Child Elements</span></span>  
  
|<span data-ttu-id="6461d-127">요소</span><span class="sxs-lookup"><span data-stu-id="6461d-127">Element</span></span>|<span data-ttu-id="6461d-128">설명</span><span class="sxs-lookup"><span data-stu-id="6461d-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6461d-129">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="6461d-129">\<certificateValidator></span></span>](certificatevalidator.md)|<span data-ttu-id="6461d-130">인증서 유효성 검사에 대 한 사용자 지정 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6461d-130">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="6461d-131">이 형식은 `certificateValidationMode` [ \<certificatevalidation >](certificatevalidation.md) 요소의 특성이 "Custom"으로 설정 된 경우에만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6461d-131">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6461d-132">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6461d-132">Parent Elements</span></span>  
  
|<span data-ttu-id="6461d-133">요소</span><span class="sxs-lookup"><span data-stu-id="6461d-133">Element</span></span>|<span data-ttu-id="6461d-134">설명</span><span class="sxs-lookup"><span data-stu-id="6461d-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6461d-135">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="6461d-135">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="6461d-136">서비스 수준 id 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6461d-136">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="6461d-137">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="6461d-137">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="6461d-138">보안 토큰 처리기의 컬렉션에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6461d-138">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6461d-139">설명</span><span class="sxs-lookup"><span data-stu-id="6461d-139">Remarks</span></span>  
 <span data-ttu-id="6461d-140">요소는 요소 아래의 서비스 수준 `<identityConfiguration>` 또는 요소의 보안 토큰 `<securityTokenHandlerConfiguration>` 처리기 컬렉션 수준에서 지정할 수 있습니다. `<certificateValidation>`</span><span class="sxs-lookup"><span data-stu-id="6461d-140">A `<certificateValidation>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="6461d-141">토큰 처리기 컬렉션의 설정은 서비스에 지정 된 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="6461d-141">Settings on a token handler collection override those specified on the service.</span></span> <span data-ttu-id="6461d-142">일부 토큰 처리기를 사용 하면 구성에서 인증서 유효성 검사 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6461d-142">Some token handlers allow you to specify certificate validation settings in configuration.</span></span> <span data-ttu-id="6461d-143">개별 토큰 처리기의 설정은 서비스 수준 및 보안 토큰 처리기 컬렉션 둘 다에서 지정 된 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="6461d-143">Settings on individual token handlers override those specified both at the service level and on the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6461d-144">예제</span><span class="sxs-lookup"><span data-stu-id="6461d-144">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```
