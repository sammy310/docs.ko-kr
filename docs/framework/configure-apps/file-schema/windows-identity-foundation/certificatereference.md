---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: c7dc9cfff15e70eff0086cfd98a19f3360ab8bb0
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423036"
---
# <a name="certificatereference"></a><span data-ttu-id="32d22-101">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="32d22-101">\<certificateReference></span></span>
<span data-ttu-id="32d22-102">찾기 및 인증서 저장소에서 X.509 인증서의 유효성을 검사 하는 데 사용 되는 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="32d22-102">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
 <span data-ttu-id="32d22-103">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="32d22-103">\<system.identityModel.services></span></span>  
<span data-ttu-id="32d22-104">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="32d22-104">\<federationConfiguration></span></span>  
<span data-ttu-id="32d22-105">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="32d22-105">\<serviceCertificate></span></span>  
<span data-ttu-id="32d22-106">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="32d22-106">\<certificateReference></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32d22-107">구문</span><span class="sxs-lookup"><span data-stu-id="32d22-107">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
      <certificateReference   
        storeName="AddressBook||AuthRoot||CertificateAuthority||Disallowed||My||Root||TrustedPeople||TrustedPublisher"  
        storeLocation="CurrentUser||LocalMachine"  
        x509FindType="FindByThumbprint||FindBySubjectName||FindBySubjectDistinguishedName||FindByIssuerName||FindByIssuerDistinguishedName||FindBySerialNumber||FindByTimeValid||FindByTimeNotYetValid||FindByTimeExpired||FindByTemplateName||FindByApplicationPolicy||FindByCertificatePolicy||FindByExtension||FindByKeyUsage||FindBySubjectKeyIdentifier"  
        findValue=xs:String  
        isChainIncluded=xs:Boolean >  
      </certificateReference>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="32d22-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="32d22-108">Attributes and Elements</span></span>  
 <span data-ttu-id="32d22-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="32d22-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="32d22-110">특성</span><span class="sxs-lookup"><span data-stu-id="32d22-110">Attributes</span></span>  
  
|<span data-ttu-id="32d22-111">특성</span><span class="sxs-lookup"><span data-stu-id="32d22-111">Attribute</span></span>|<span data-ttu-id="32d22-112">설명</span><span class="sxs-lookup"><span data-stu-id="32d22-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="32d22-113">storeName</span><span class="sxs-lookup"><span data-stu-id="32d22-113">storeName</span></span>|<span data-ttu-id="32d22-114">X.509 인증서 저장소의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="32d22-114">The name of the X.509 certificate store.</span></span> <span data-ttu-id="32d22-115">기본값은 "My"입니다.</span><span class="sxs-lookup"><span data-stu-id="32d22-115">The default is "My".</span></span> <span data-ttu-id="32d22-116">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="32d22-116">Optional.</span></span>|  
|<span data-ttu-id="32d22-117">storeLocation</span><span class="sxs-lookup"><span data-stu-id="32d22-117">storeLocation</span></span>|<span data-ttu-id="32d22-118"><xref:System.Security.Cryptography.X509Certificates.StoreLocation> X.509 인증서 저장소의 위치를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="32d22-118">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="32d22-119">기본값은 "LocalMachine"입니다.</span><span class="sxs-lookup"><span data-stu-id="32d22-119">The default value is "LocalMachine".</span></span> <span data-ttu-id="32d22-120">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="32d22-120">Optional.</span></span>|  
|<span data-ttu-id="32d22-121">x509FindType</span><span class="sxs-lookup"><span data-stu-id="32d22-121">x509FindType</span></span>|<span data-ttu-id="32d22-122"><xref:System.Security.Cryptography.X509Certificates.X509FindType> 를 실행 해야 하는 검색의 유형을 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="32d22-122">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="32d22-123">기본값은 "FindBySubjectDistinguishedName"입니다.</span><span class="sxs-lookup"><span data-stu-id="32d22-123">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="32d22-124">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="32d22-124">Optional.</span></span>|  
|<span data-ttu-id="32d22-125">findValue</span><span class="sxs-lookup"><span data-stu-id="32d22-125">findValue</span></span>|<span data-ttu-id="32d22-126">X.509 인증서 저장소에서 검색할 값입니다.</span><span class="sxs-lookup"><span data-stu-id="32d22-126">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="32d22-127">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="32d22-127">Optional.</span></span>|  
|<span data-ttu-id="32d22-128">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="32d22-128">isChainIncluded</span></span>|<span data-ttu-id="32d22-129">인증서 체인을 사용 하 여 유효성 검사를 수행할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="32d22-129">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="32d22-130">기본값은 "true"; 유효성 검사 인증서 체인을 사용 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32d22-130">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="32d22-131">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="32d22-131">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="32d22-132">자식 요소</span><span class="sxs-lookup"><span data-stu-id="32d22-132">Child Elements</span></span>  
 <span data-ttu-id="32d22-133">없음</span><span class="sxs-lookup"><span data-stu-id="32d22-133">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="32d22-134">부모 요소</span><span class="sxs-lookup"><span data-stu-id="32d22-134">Parent Elements</span></span>  
  
|<span data-ttu-id="32d22-135">요소</span><span class="sxs-lookup"><span data-stu-id="32d22-135">Element</span></span>|<span data-ttu-id="32d22-136">설명</span><span class="sxs-lookup"><span data-stu-id="32d22-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="32d22-137">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="32d22-137">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|<span data-ttu-id="32d22-138">암호화 및 토큰 암호 해독에 사용 되는 인증서를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="32d22-138">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32d22-139">설명</span><span class="sxs-lookup"><span data-stu-id="32d22-139">Remarks</span></span>  
 <span data-ttu-id="32d22-140">`<certificateReference>` 요소 찾기 및 인증서 저장소에서 X.509 인증서의 유효성을 검사 하는 데 사용 되는 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="32d22-140">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="32d22-141">자식 요소로 지정 된 경우는 `<serviceCertificate>` 요소를 암호화 및 토큰 암호 해독에 사용 되는 X.509 인증서의 위치 및 인증 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="32d22-141">When it is specified as the child element of the `<serviceCertificate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="32d22-142">합니다 `<certificateReference>` 에서 요소가 표시 되는 <xref:System.ServiceModel.Configuration.CertificateReferenceElement> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="32d22-142">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>
