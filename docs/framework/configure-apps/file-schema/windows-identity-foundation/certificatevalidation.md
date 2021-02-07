---
description: 다음에 대해 자세히 알아보세요. <certificateValidation>
title: <certificateValidation>
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
ms.openlocfilehash: a12e46487b4fb2ac8071ba1cf9bc5c6057ded060
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740069"
---
# \<certificateValidation>

<span data-ttu-id="e6756-102">토큰 처리기에서 인증서의 유효성을 검사 하는 데 사용 하는 설정을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6756-102">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="e6756-103">이러한 설정은 고유한 유효성 검사기를 사용 하 여 특정 처리기를 구성 하는 경우 재정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6756-103">These settings are overridden if a specific handler is configured with its own validator.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateValidation>**  
  
## <a name="syntax"></a><span data-ttu-id="e6756-104">구문</span><span class="sxs-lookup"><span data-stu-id="e6756-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e6756-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e6756-105">Attributes and Elements</span></span>  

 <span data-ttu-id="e6756-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e6756-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e6756-107">특성</span><span class="sxs-lookup"><span data-stu-id="e6756-107">Attributes</span></span>  
  
|<span data-ttu-id="e6756-108">attribute</span><span class="sxs-lookup"><span data-stu-id="e6756-108">Attribute</span></span>|<span data-ttu-id="e6756-109">설명</span><span class="sxs-lookup"><span data-stu-id="e6756-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e6756-110">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="e6756-110">certificateValidationMode</span></span>|<span data-ttu-id="e6756-111"><xref:System.ServiceModel.Security.X509CertificateValidationMode>X.509 인증서에 사용할 유효성 검사 모드를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e6756-111">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="e6756-112">기본값은 "PeerOrChainTrust"입니다.</span><span class="sxs-lookup"><span data-stu-id="e6756-112">The default value is "PeerOrChainTrust".</span></span> <span data-ttu-id="e6756-113">사용자 지정 유효성 검사기를 지정 하려면이 특성을 "Custom"으로 설정 하 고 요소를 사용 하 여 유효성 검사기를 지정 합니다 [\<certificateValidator>](certificatevalidator.md) .</span><span class="sxs-lookup"><span data-stu-id="e6756-113">To specify a custom validator, set this attribute to "Custom" and specify the validator using the [\<certificateValidator>](certificatevalidator.md) element.</span></span> <span data-ttu-id="e6756-114">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="e6756-114">Optional.</span></span>|  
|<span data-ttu-id="e6756-115">revocationMode</span><span class="sxs-lookup"><span data-stu-id="e6756-115">revocationMode</span></span>|<span data-ttu-id="e6756-116"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>X.509 인증서에 사용할 해지 모드를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e6756-116">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="e6756-117">기본값은 "Online"입니다.</span><span class="sxs-lookup"><span data-stu-id="e6756-117">The default value is "Online".</span></span> <span data-ttu-id="e6756-118">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="e6756-118">Optional.</span></span>|  
|<span data-ttu-id="e6756-119">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="e6756-119">trustedStoreLocation</span></span>|<span data-ttu-id="e6756-120"><xref:System.Security.Cryptography.X509Certificates.StoreLocation>X.509 인증서 저장소를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e6756-120">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="e6756-121">기본값은 "LocalMachine"입니다.</span><span class="sxs-lookup"><span data-stu-id="e6756-121">The default value is "LocalMachine".</span></span> <span data-ttu-id="e6756-122">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="e6756-122">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e6756-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e6756-123">Child Elements</span></span>  
  
|<span data-ttu-id="e6756-124">요소</span><span class="sxs-lookup"><span data-stu-id="e6756-124">Element</span></span>|<span data-ttu-id="e6756-125">설명</span><span class="sxs-lookup"><span data-stu-id="e6756-125">Description</span></span>|  
|-------------|-----------------|  
|[\<certificateValidator>](certificatevalidator.md)|<span data-ttu-id="e6756-126">인증서 유효성 검사에 대 한 사용자 지정 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6756-126">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="e6756-127">이 형식은 `certificateValidationMode` [\<certificateValidation>](certificatevalidation.md) 요소의 특성이 "Custom"으로 설정 된 경우에만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6756-127">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e6756-128">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e6756-128">Parent Elements</span></span>  
  
|<span data-ttu-id="e6756-129">요소</span><span class="sxs-lookup"><span data-stu-id="e6756-129">Element</span></span>|<span data-ttu-id="e6756-130">설명</span><span class="sxs-lookup"><span data-stu-id="e6756-130">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="e6756-131">서비스 수준 id 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6756-131">Specifies service-level identity settings.</span></span>|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="e6756-132">보안 토큰 처리기의 컬렉션에 대 한 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6756-132">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6756-133">설명</span><span class="sxs-lookup"><span data-stu-id="e6756-133">Remarks</span></span>  

 <span data-ttu-id="e6756-134">요소는 요소 아래의 `<certificateValidation>` 서비스 수준 `<identityConfiguration>` 또는 요소의 보안 토큰 처리기 컬렉션 수준에서 지정할 수 있습니다 `<securityTokenHandlerConfiguration>` .</span><span class="sxs-lookup"><span data-stu-id="e6756-134">A `<certificateValidation>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="e6756-135">토큰 처리기 컬렉션의 설정은 서비스에 지정 된 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6756-135">Settings on a token handler collection override those specified on the service.</span></span> <span data-ttu-id="e6756-136">일부 토큰 처리기를 사용 하면 구성에서 인증서 유효성 검사 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6756-136">Some token handlers allow you to specify certificate validation settings in configuration.</span></span> <span data-ttu-id="e6756-137">개별 토큰 처리기의 설정은 서비스 수준 및 보안 토큰 처리기 컬렉션 둘 다에서 지정 된 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6756-137">Settings on individual token handlers override those specified both at the service level and on the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6756-138">예제</span><span class="sxs-lookup"><span data-stu-id="e6756-138">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```
