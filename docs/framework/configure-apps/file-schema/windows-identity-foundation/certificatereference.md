---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: 47d432a84d070476ddffd9b98a4ba46d8163bdc3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152816"
---
# \<certificateReference>
<span data-ttu-id="1f9ba-101">인증서 저장소에서 x.509 인증서를 찾고 유효성을 검사 하는 데 사용 되는 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f9ba-101">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateReference>**  
  
## <a name="syntax"></a><span data-ttu-id="1f9ba-102">구문</span><span class="sxs-lookup"><span data-stu-id="1f9ba-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1f9ba-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1f9ba-103">Attributes and Elements</span></span>  
 <span data-ttu-id="1f9ba-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1f9ba-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1f9ba-105">특성</span><span class="sxs-lookup"><span data-stu-id="1f9ba-105">Attributes</span></span>  
  
|<span data-ttu-id="1f9ba-106">attribute</span><span class="sxs-lookup"><span data-stu-id="1f9ba-106">Attribute</span></span>|<span data-ttu-id="1f9ba-107">Description</span><span class="sxs-lookup"><span data-stu-id="1f9ba-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1f9ba-108">storeName</span><span class="sxs-lookup"><span data-stu-id="1f9ba-108">storeName</span></span>|<span data-ttu-id="1f9ba-109">X.509 인증서 저장소 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1f9ba-109">The name of the X.509 certificate store.</span></span> <span data-ttu-id="1f9ba-110">기본값은 "My"입니다.</span><span class="sxs-lookup"><span data-stu-id="1f9ba-110">The default is "My".</span></span> <span data-ttu-id="1f9ba-111">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="1f9ba-111">Optional.</span></span>|  
|<span data-ttu-id="1f9ba-112">storeLocation</span><span class="sxs-lookup"><span data-stu-id="1f9ba-112">storeLocation</span></span>|<span data-ttu-id="1f9ba-113"><xref:System.Security.Cryptography.X509Certificates.StoreLocation>X.509 인증서 저장소의 위치를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1f9ba-113">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="1f9ba-114">기본값은 "LocalMachine"입니다.</span><span class="sxs-lookup"><span data-stu-id="1f9ba-114">The default value is "LocalMachine".</span></span> <span data-ttu-id="1f9ba-115">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="1f9ba-115">Optional.</span></span>|  
|<span data-ttu-id="1f9ba-116">x509FindType</span><span class="sxs-lookup"><span data-stu-id="1f9ba-116">x509FindType</span></span>|<span data-ttu-id="1f9ba-117"><xref:System.Security.Cryptography.X509Certificates.X509FindType>실행할 검색 유형을 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1f9ba-117">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="1f9ba-118">기본값은 "FindBySubjectDistinguishedName"입니다.</span><span class="sxs-lookup"><span data-stu-id="1f9ba-118">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="1f9ba-119">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="1f9ba-119">Optional.</span></span>|  
|<span data-ttu-id="1f9ba-120">findValue</span><span class="sxs-lookup"><span data-stu-id="1f9ba-120">findValue</span></span>|<span data-ttu-id="1f9ba-121">X.509 인증서 저장소에서 검색할 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1f9ba-121">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="1f9ba-122">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="1f9ba-122">Optional.</span></span>|  
|<span data-ttu-id="1f9ba-123">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="1f9ba-123">isChainIncluded</span></span>|<span data-ttu-id="1f9ba-124">인증서 체인을 사용 하 여 유효성 검사를 수행할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f9ba-124">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="1f9ba-125">기본값은 "true"입니다. 유효성 검사는 인증서 체인을 사용 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f9ba-125">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="1f9ba-126">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="1f9ba-126">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1f9ba-127">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1f9ba-127">Child Elements</span></span>  
 <span data-ttu-id="1f9ba-128">None</span><span class="sxs-lookup"><span data-stu-id="1f9ba-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1f9ba-129">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1f9ba-129">Parent Elements</span></span>  
  
|<span data-ttu-id="1f9ba-130">요소</span><span class="sxs-lookup"><span data-stu-id="1f9ba-130">Element</span></span>|<span data-ttu-id="1f9ba-131">Description</span><span class="sxs-lookup"><span data-stu-id="1f9ba-131">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate.md)|<span data-ttu-id="1f9ba-132">토큰을 암호화 하 고 해독 하는 데 사용 되는 인증서를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f9ba-132">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f9ba-133">설명</span><span class="sxs-lookup"><span data-stu-id="1f9ba-133">Remarks</span></span>  
 <span data-ttu-id="1f9ba-134">`<certificateReference>`요소는 인증서 저장소에서 x.509 인증서를 찾고 유효성을 검사 하는 데 사용 되는 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f9ba-134">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="1f9ba-135">요소를 요소의 자식 요소로 지정 하면 `<serviceCertificate>` 토큰을 암호화 하 고 해독 하는 데 사용 되는 x.509 인증서의 위치 및 확인 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f9ba-135">When it is specified as the child element of the `<serviceCertificate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="1f9ba-136">합니다 `<certificateReference>` 에서 요소가 표시 되는 <xref:System.ServiceModel.Configuration.CertificateReferenceElement> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="1f9ba-136">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>
