---
description: 다음에 대해 자세히 알아보세요. <certificateReference>
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: 3404d44457849fb78ae88617d049a2199f2b5509
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99681788"
---
# \<certificateReference>

<span data-ttu-id="c5b1c-102">인증서 저장소에서 x.509 인증서를 찾고 유효성을 검사 하는 데 사용 되는 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b1c-102">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateReference>**  
  
## <a name="syntax"></a><span data-ttu-id="c5b1c-103">구문</span><span class="sxs-lookup"><span data-stu-id="c5b1c-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c5b1c-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c5b1c-104">Attributes and Elements</span></span>  

 <span data-ttu-id="c5b1c-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b1c-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c5b1c-106">특성</span><span class="sxs-lookup"><span data-stu-id="c5b1c-106">Attributes</span></span>  
  
|<span data-ttu-id="c5b1c-107">attribute</span><span class="sxs-lookup"><span data-stu-id="c5b1c-107">Attribute</span></span>|<span data-ttu-id="c5b1c-108">설명</span><span class="sxs-lookup"><span data-stu-id="c5b1c-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c5b1c-109">storeName</span><span class="sxs-lookup"><span data-stu-id="c5b1c-109">storeName</span></span>|<span data-ttu-id="c5b1c-110">X.509 인증서 저장소 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c5b1c-110">The name of the X.509 certificate store.</span></span> <span data-ttu-id="c5b1c-111">기본값은 "My"입니다.</span><span class="sxs-lookup"><span data-stu-id="c5b1c-111">The default is "My".</span></span> <span data-ttu-id="c5b1c-112">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c5b1c-112">Optional.</span></span>|  
|<span data-ttu-id="c5b1c-113">storeLocation</span><span class="sxs-lookup"><span data-stu-id="c5b1c-113">storeLocation</span></span>|<span data-ttu-id="c5b1c-114"><xref:System.Security.Cryptography.X509Certificates.StoreLocation>X.509 인증서 저장소의 위치를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c5b1c-114">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="c5b1c-115">기본값은 "LocalMachine"입니다.</span><span class="sxs-lookup"><span data-stu-id="c5b1c-115">The default value is "LocalMachine".</span></span> <span data-ttu-id="c5b1c-116">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c5b1c-116">Optional.</span></span>|  
|<span data-ttu-id="c5b1c-117">x509FindType</span><span class="sxs-lookup"><span data-stu-id="c5b1c-117">x509FindType</span></span>|<span data-ttu-id="c5b1c-118"><xref:System.Security.Cryptography.X509Certificates.X509FindType>실행할 검색 유형을 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c5b1c-118">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="c5b1c-119">기본값은 "FindBySubjectDistinguishedName"입니다.</span><span class="sxs-lookup"><span data-stu-id="c5b1c-119">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="c5b1c-120">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c5b1c-120">Optional.</span></span>|  
|<span data-ttu-id="c5b1c-121">findValue</span><span class="sxs-lookup"><span data-stu-id="c5b1c-121">findValue</span></span>|<span data-ttu-id="c5b1c-122">X.509 인증서 저장소에서 검색할 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c5b1c-122">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="c5b1c-123">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c5b1c-123">Optional.</span></span>|  
|<span data-ttu-id="c5b1c-124">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="c5b1c-124">isChainIncluded</span></span>|<span data-ttu-id="c5b1c-125">인증서 체인을 사용 하 여 유효성 검사를 수행할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b1c-125">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="c5b1c-126">기본값은 "true"입니다. 유효성 검사는 인증서 체인을 사용 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5b1c-126">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="c5b1c-127">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c5b1c-127">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c5b1c-128">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c5b1c-128">Child Elements</span></span>  

 <span data-ttu-id="c5b1c-129">없음</span><span class="sxs-lookup"><span data-stu-id="c5b1c-129">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c5b1c-130">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c5b1c-130">Parent Elements</span></span>  
  
|<span data-ttu-id="c5b1c-131">요소</span><span class="sxs-lookup"><span data-stu-id="c5b1c-131">Element</span></span>|<span data-ttu-id="c5b1c-132">설명</span><span class="sxs-lookup"><span data-stu-id="c5b1c-132">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate.md)|<span data-ttu-id="c5b1c-133">토큰을 암호화 하 고 해독 하는 데 사용 되는 인증서를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b1c-133">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5b1c-134">설명</span><span class="sxs-lookup"><span data-stu-id="c5b1c-134">Remarks</span></span>  

 <span data-ttu-id="c5b1c-135">`<certificateReference>`요소는 인증서 저장소에서 x.509 인증서를 찾고 유효성을 검사 하는 데 사용 되는 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b1c-135">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="c5b1c-136">요소를 요소의 자식 요소로 지정 하면 `<serviceCertificate>` 토큰을 암호화 하 고 해독 하는 데 사용 되는 x.509 인증서의 위치 및 확인 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b1c-136">When it is specified as the child element of the `<serviceCertificate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="c5b1c-137">합니다 `<certificateReference>` 에서 요소가 표시 되는 <xref:System.ServiceModel.Configuration.CertificateReferenceElement> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="c5b1c-137">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>
