---
title: <certificateValidation>
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
ms.openlocfilehash: c2d1a5d36cb5616ef06eedc093dd70a68a164a81
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252129"
---
# <a name="certificatevalidation"></a><span data-ttu-id="28ef8-101">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="28ef8-101">\<certificateValidation></span></span>
<span data-ttu-id="28ef8-102">토큰 처리기에서 인증서의 유효성을 검사 하는 데 사용 하는 설정을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="28ef8-102">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="28ef8-103">이러한 설정은 고유한 유효성 검사기를 사용 하 여 특정 처리기를 구성 하는 경우 재정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="28ef8-103">These settings are overridden if a specific handler is configured with its own validator.</span></span>  
  
<span data-ttu-id="28ef8-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="28ef8-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="28ef8-105">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="28ef8-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="28ef8-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="28ef8-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="28ef8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<certificateValidation >**</span><span class="sxs-lookup"><span data-stu-id="28ef8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateValidation>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28ef8-108">구문</span><span class="sxs-lookup"><span data-stu-id="28ef8-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="28ef8-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="28ef8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="28ef8-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="28ef8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="28ef8-111">특성</span><span class="sxs-lookup"><span data-stu-id="28ef8-111">Attributes</span></span>  
  
|<span data-ttu-id="28ef8-112">특성</span><span class="sxs-lookup"><span data-stu-id="28ef8-112">Attribute</span></span>|<span data-ttu-id="28ef8-113">Description</span><span class="sxs-lookup"><span data-stu-id="28ef8-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="28ef8-114">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="28ef8-114">certificateValidationMode</span></span>|<span data-ttu-id="28ef8-115">X.509 인증서에 사용할 유효성 검사 모드를 지정 하는 값입니다.<xref:System.ServiceModel.Security.X509CertificateValidationMode></span><span class="sxs-lookup"><span data-stu-id="28ef8-115">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="28ef8-116">기본값은 "PeerOrChainTrust"입니다.</span><span class="sxs-lookup"><span data-stu-id="28ef8-116">The default value is "PeerOrChainTrust".</span></span> <span data-ttu-id="28ef8-117">사용자 지정 유효성 검사기를 지정 하려면이 특성을 "custom"으로 설정 하 고 [ \<certificateValidator >](certificatevalidator.md) 요소를 사용 하 여 유효성 검사기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="28ef8-117">To specify a custom validator, set this attribute to "Custom" and specify the validator using the [\<certificateValidator>](certificatevalidator.md) element.</span></span> <span data-ttu-id="28ef8-118">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="28ef8-118">Optional.</span></span>|  
|<span data-ttu-id="28ef8-119">revocationMode</span><span class="sxs-lookup"><span data-stu-id="28ef8-119">revocationMode</span></span>|<span data-ttu-id="28ef8-120">X.509 인증서에 사용할 해지 모드를 지정 하는 값입니다.<xref:System.Security.Cryptography.X509Certificates.X509RevocationMode></span><span class="sxs-lookup"><span data-stu-id="28ef8-120">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="28ef8-121">기본값은 "Online"입니다.</span><span class="sxs-lookup"><span data-stu-id="28ef8-121">The default value is "Online".</span></span> <span data-ttu-id="28ef8-122">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="28ef8-122">Optional.</span></span>|  
|<span data-ttu-id="28ef8-123">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="28ef8-123">trustedStoreLocation</span></span>|<span data-ttu-id="28ef8-124">X.509 인증서 저장소를 지정 하는 값입니다.<xref:System.Security.Cryptography.X509Certificates.StoreLocation></span><span class="sxs-lookup"><span data-stu-id="28ef8-124">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="28ef8-125">기본값은 "LocalMachine"입니다.</span><span class="sxs-lookup"><span data-stu-id="28ef8-125">The default value is "LocalMachine".</span></span> <span data-ttu-id="28ef8-126">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="28ef8-126">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="28ef8-127">자식 요소</span><span class="sxs-lookup"><span data-stu-id="28ef8-127">Child Elements</span></span>  
  
|<span data-ttu-id="28ef8-128">요소</span><span class="sxs-lookup"><span data-stu-id="28ef8-128">Element</span></span>|<span data-ttu-id="28ef8-129">Description</span><span class="sxs-lookup"><span data-stu-id="28ef8-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="28ef8-130">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="28ef8-130">\<certificateValidator></span></span>](certificatevalidator.md)|<span data-ttu-id="28ef8-131">인증서 유효성 검사에 대 한 사용자 지정 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="28ef8-131">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="28ef8-132">이 형식은 `certificateValidationMode` [ \<certificatevalidation >](certificatevalidation.md) 요소의 특성이 "Custom"으로 설정 된 경우에만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="28ef8-132">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="28ef8-133">부모 요소</span><span class="sxs-lookup"><span data-stu-id="28ef8-133">Parent Elements</span></span>  
  
|<span data-ttu-id="28ef8-134">요소</span><span class="sxs-lookup"><span data-stu-id="28ef8-134">Element</span></span>|<span data-ttu-id="28ef8-135">설명</span><span class="sxs-lookup"><span data-stu-id="28ef8-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="28ef8-136">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="28ef8-136">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="28ef8-137">서비스 수준 id 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="28ef8-137">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="28ef8-138">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="28ef8-138">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="28ef8-139">보안 토큰 처리기의 컬렉션에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="28ef8-139">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28ef8-140">설명</span><span class="sxs-lookup"><span data-stu-id="28ef8-140">Remarks</span></span>  
 <span data-ttu-id="28ef8-141">요소는 요소 아래의 서비스 수준 `<identityConfiguration>` 또는 요소의 보안 토큰 `<securityTokenHandlerConfiguration>` 처리기 컬렉션 수준에서 지정할 수 있습니다. `<certificateValidation>`</span><span class="sxs-lookup"><span data-stu-id="28ef8-141">A `<certificateValidation>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="28ef8-142">토큰 처리기 컬렉션의 설정은 서비스에 지정 된 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="28ef8-142">Settings on a token handler collection override those specified on the service.</span></span> <span data-ttu-id="28ef8-143">일부 토큰 처리기를 사용 하면 구성에서 인증서 유효성 검사 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28ef8-143">Some token handlers allow you to specify certificate validation settings in configuration.</span></span> <span data-ttu-id="28ef8-144">개별 토큰 처리기의 설정은 서비스 수준 및 보안 토큰 처리기 컬렉션 둘 다에서 지정 된 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="28ef8-144">Settings on individual token handlers override those specified both at the service level and on the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28ef8-145">예제</span><span class="sxs-lookup"><span data-stu-id="28ef8-145">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```
