---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: 782ca3344774b8412a18e3cf13bff5f969751ea3
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252150"
---
# <a name="certificatereference"></a><span data-ttu-id="9db5d-101">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="9db5d-101">\<certificateReference></span></span>
<span data-ttu-id="9db5d-102">인증서 저장소에서 x.509 인증서를 찾고 유효성을 검사 하는 데 사용 되는 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9db5d-102">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
<span data-ttu-id="9db5d-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9db5d-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9db5d-104">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel-services.md)</span><span class="sxs-lookup"><span data-stu-id="9db5d-104">&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)</span></span>\
<span data-ttu-id="9db5d-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<federationConfiguration >** ](federationconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="9db5d-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)</span></span>\
<span data-ttu-id="9db5d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCertificate >** ](servicecertificate.md)</span><span class="sxs-lookup"><span data-stu-id="9db5d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate.md)</span></span>\
<span data-ttu-id="9db5d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<certificateReference >**</span><span class="sxs-lookup"><span data-stu-id="9db5d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateReference>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9db5d-108">구문</span><span class="sxs-lookup"><span data-stu-id="9db5d-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9db5d-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9db5d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9db5d-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9db5d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9db5d-111">특성</span><span class="sxs-lookup"><span data-stu-id="9db5d-111">Attributes</span></span>  
  
|<span data-ttu-id="9db5d-112">특성</span><span class="sxs-lookup"><span data-stu-id="9db5d-112">Attribute</span></span>|<span data-ttu-id="9db5d-113">설명</span><span class="sxs-lookup"><span data-stu-id="9db5d-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9db5d-114">storeName</span><span class="sxs-lookup"><span data-stu-id="9db5d-114">storeName</span></span>|<span data-ttu-id="9db5d-115">X.509 인증서 저장소의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9db5d-115">The name of the X.509 certificate store.</span></span> <span data-ttu-id="9db5d-116">기본값은 "My"입니다.</span><span class="sxs-lookup"><span data-stu-id="9db5d-116">The default is "My".</span></span> <span data-ttu-id="9db5d-117">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="9db5d-117">Optional.</span></span>|  
|<span data-ttu-id="9db5d-118">storeLocation</span><span class="sxs-lookup"><span data-stu-id="9db5d-118">storeLocation</span></span>|<span data-ttu-id="9db5d-119">X.509 인증서 저장소의 위치를 지정 하는 값입니다.<xref:System.Security.Cryptography.X509Certificates.StoreLocation></span><span class="sxs-lookup"><span data-stu-id="9db5d-119">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="9db5d-120">기본값은 "LocalMachine"입니다.</span><span class="sxs-lookup"><span data-stu-id="9db5d-120">The default value is "LocalMachine".</span></span> <span data-ttu-id="9db5d-121">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="9db5d-121">Optional.</span></span>|  
|<span data-ttu-id="9db5d-122">x509FindType</span><span class="sxs-lookup"><span data-stu-id="9db5d-122">x509FindType</span></span>|<span data-ttu-id="9db5d-123">실행할 검색 유형을 지정 하는 값입니다.<xref:System.Security.Cryptography.X509Certificates.X509FindType></span><span class="sxs-lookup"><span data-stu-id="9db5d-123">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="9db5d-124">기본값은 "FindBySubjectDistinguishedName"입니다.</span><span class="sxs-lookup"><span data-stu-id="9db5d-124">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="9db5d-125">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="9db5d-125">Optional.</span></span>|  
|<span data-ttu-id="9db5d-126">findValue</span><span class="sxs-lookup"><span data-stu-id="9db5d-126">findValue</span></span>|<span data-ttu-id="9db5d-127">X.509 인증서 저장소에서 검색할 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9db5d-127">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="9db5d-128">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="9db5d-128">Optional.</span></span>|  
|<span data-ttu-id="9db5d-129">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="9db5d-129">isChainIncluded</span></span>|<span data-ttu-id="9db5d-130">인증서 체인을 사용 하 여 유효성 검사를 수행할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9db5d-130">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="9db5d-131">기본값은 "true"입니다. 유효성 검사는 인증서 체인을 사용 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9db5d-131">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="9db5d-132">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="9db5d-132">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9db5d-133">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9db5d-133">Child Elements</span></span>  
 <span data-ttu-id="9db5d-134">없음</span><span class="sxs-lookup"><span data-stu-id="9db5d-134">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9db5d-135">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9db5d-135">Parent Elements</span></span>  
  
|<span data-ttu-id="9db5d-136">요소</span><span class="sxs-lookup"><span data-stu-id="9db5d-136">Element</span></span>|<span data-ttu-id="9db5d-137">Description</span><span class="sxs-lookup"><span data-stu-id="9db5d-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9db5d-138">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="9db5d-138">\<serviceCertificate></span></span>](servicecertificate.md)|<span data-ttu-id="9db5d-139">토큰을 암호화 하 고 해독 하는 데 사용 되는 인증서를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9db5d-139">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9db5d-140">설명</span><span class="sxs-lookup"><span data-stu-id="9db5d-140">Remarks</span></span>  
 <span data-ttu-id="9db5d-141">요소 `<certificateReference>` 는 인증서 저장소에서 x.509 인증서를 찾고 유효성을 검사 하는 데 사용 되는 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9db5d-141">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="9db5d-142">`<serviceCertificate>` 요소를 요소의 자식 요소로 지정 하면 토큰을 암호화 하 고 해독 하는 데 사용 되는 x.509 인증서의 위치 및 확인 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9db5d-142">When it is specified as the child element of the `<serviceCertificate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="9db5d-143">합니다 `<certificateReference>` 에서 요소가 표시 되는 <xref:System.ServiceModel.Configuration.CertificateReferenceElement> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="9db5d-143">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>
