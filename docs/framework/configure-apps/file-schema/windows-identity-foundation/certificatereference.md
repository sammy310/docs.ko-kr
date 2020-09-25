---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: c21e5186b8afdf8c72cbfc605af94c95bc2bc0d5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201381"
---
# \<certificateReference>

<span data-ttu-id="58613-101">인증서 저장소에서 x.509 인증서를 찾고 유효성을 검사 하는 데 사용 되는 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="58613-101">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateReference>**  
  
## <a name="syntax"></a><span data-ttu-id="58613-102">구문</span><span class="sxs-lookup"><span data-stu-id="58613-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="58613-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="58613-103">Attributes and Elements</span></span>  

 <span data-ttu-id="58613-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="58613-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="58613-105">특성</span><span class="sxs-lookup"><span data-stu-id="58613-105">Attributes</span></span>  
  
|<span data-ttu-id="58613-106">attribute</span><span class="sxs-lookup"><span data-stu-id="58613-106">Attribute</span></span>|<span data-ttu-id="58613-107">설명</span><span class="sxs-lookup"><span data-stu-id="58613-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="58613-108">storeName</span><span class="sxs-lookup"><span data-stu-id="58613-108">storeName</span></span>|<span data-ttu-id="58613-109">X.509 인증서 저장소 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="58613-109">The name of the X.509 certificate store.</span></span> <span data-ttu-id="58613-110">기본값은 "My"입니다.</span><span class="sxs-lookup"><span data-stu-id="58613-110">The default is "My".</span></span> <span data-ttu-id="58613-111">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="58613-111">Optional.</span></span>|  
|<span data-ttu-id="58613-112">storeLocation</span><span class="sxs-lookup"><span data-stu-id="58613-112">storeLocation</span></span>|<span data-ttu-id="58613-113"><xref:System.Security.Cryptography.X509Certificates.StoreLocation>X.509 인증서 저장소의 위치를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="58613-113">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="58613-114">기본값은 "LocalMachine"입니다.</span><span class="sxs-lookup"><span data-stu-id="58613-114">The default value is "LocalMachine".</span></span> <span data-ttu-id="58613-115">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="58613-115">Optional.</span></span>|  
|<span data-ttu-id="58613-116">x509FindType</span><span class="sxs-lookup"><span data-stu-id="58613-116">x509FindType</span></span>|<span data-ttu-id="58613-117"><xref:System.Security.Cryptography.X509Certificates.X509FindType>실행할 검색 유형을 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="58613-117">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="58613-118">기본값은 "FindBySubjectDistinguishedName"입니다.</span><span class="sxs-lookup"><span data-stu-id="58613-118">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="58613-119">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="58613-119">Optional.</span></span>|  
|<span data-ttu-id="58613-120">findValue</span><span class="sxs-lookup"><span data-stu-id="58613-120">findValue</span></span>|<span data-ttu-id="58613-121">X.509 인증서 저장소에서 검색할 값입니다.</span><span class="sxs-lookup"><span data-stu-id="58613-121">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="58613-122">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="58613-122">Optional.</span></span>|  
|<span data-ttu-id="58613-123">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="58613-123">isChainIncluded</span></span>|<span data-ttu-id="58613-124">인증서 체인을 사용 하 여 유효성 검사를 수행할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="58613-124">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="58613-125">기본값은 "true"입니다. 유효성 검사는 인증서 체인을 사용 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58613-125">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="58613-126">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="58613-126">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="58613-127">자식 요소</span><span class="sxs-lookup"><span data-stu-id="58613-127">Child Elements</span></span>  

 <span data-ttu-id="58613-128">없음</span><span class="sxs-lookup"><span data-stu-id="58613-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="58613-129">부모 요소</span><span class="sxs-lookup"><span data-stu-id="58613-129">Parent Elements</span></span>  
  
|<span data-ttu-id="58613-130">요소</span><span class="sxs-lookup"><span data-stu-id="58613-130">Element</span></span>|<span data-ttu-id="58613-131">설명</span><span class="sxs-lookup"><span data-stu-id="58613-131">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate.md)|<span data-ttu-id="58613-132">토큰을 암호화 하 고 해독 하는 데 사용 되는 인증서를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="58613-132">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58613-133">설명</span><span class="sxs-lookup"><span data-stu-id="58613-133">Remarks</span></span>  

 <span data-ttu-id="58613-134">`<certificateReference>`요소는 인증서 저장소에서 x.509 인증서를 찾고 유효성을 검사 하는 데 사용 되는 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="58613-134">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="58613-135">요소를 요소의 자식 요소로 지정 하면 `<serviceCertificate>` 토큰을 암호화 하 고 해독 하는 데 사용 되는 x.509 인증서의 위치 및 확인 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="58613-135">When it is specified as the child element of the `<serviceCertificate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="58613-136">합니다 `<certificateReference>` 에서 요소가 표시 되는 <xref:System.ServiceModel.Configuration.CertificateReferenceElement> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="58613-136">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>
