---
title: <certificate>of <clientCertificate> 요소
ms.date: 03/30/2017
ms.assetid: 00297efb-a7f2-4e03-bc2b-943d545610fc
ms.openlocfilehash: d0c4ef9d3657d2dfa787feb3576beda09d1997a3
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400539"
---
# <a name="certificate-of-clientcertificate-element"></a><span data-ttu-id="04969-102">\<\<clientCertificate > 요소의 인증서 ></span><span class="sxs-lookup"><span data-stu-id="04969-102">\<certificate> of \<clientCertificate> Element</span></span>
<span data-ttu-id="04969-103">메시지 서명 및 암호화에 사용되는 X.509 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="04969-103">Specifies an X.509 certificate used to sign and encrypt messages.</span></span>  
  
<span data-ttu-id="04969-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="04969-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="04969-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="04969-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="04969-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="04969-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="04969-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="04969-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="04969-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="04969-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="04969-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCredentials >** ](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="04969-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="04969-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCertificate >** ](clientcertificate-of-servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="04969-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCertificate>**](clientcertificate-of-servicecredentials.md)</span></span>\
<span data-ttu-id="04969-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<인증서 >**</span><span class="sxs-lookup"><span data-stu-id="04969-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04969-112">구문</span><span class="sxs-lookup"><span data-stu-id="04969-112">Syntax</span></span>  
  
```xml  
<certificate findValue="String"
             storeLocation = "CurrentUser/LocalMachine"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="04969-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="04969-113">Attributes and Elements</span></span>  
 <span data-ttu-id="04969-114">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="04969-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="04969-115">특성</span><span class="sxs-lookup"><span data-stu-id="04969-115">Attributes</span></span>  
  
|<span data-ttu-id="04969-116">특성</span><span class="sxs-lookup"><span data-stu-id="04969-116">Attribute</span></span>|<span data-ttu-id="04969-117">설명</span><span class="sxs-lookup"><span data-stu-id="04969-117">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="04969-118">X.509 인증서 저장소에서 검색할 값을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="04969-118">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="04969-119">이 특성에 포함된 형식은 지정된 X509FindType에 대한 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04969-119">The type contained in the attribute must satisfy the requirements of the specified X509FindType.</span></span> <span data-ttu-id="04969-120">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="04969-120">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="04969-121">클라이언트가 서버 인증서의 유효성을 검사하는 데 사용하는 X.509 인증서 저장소 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="04969-121">Specifies the location of the X.509 certificate store that the client uses to validate the server’s certificate against.</span></span> <span data-ttu-id="04969-122">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="04969-122">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="04969-123">-LocalMachine: 로컬 컴퓨터에 할당 된 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="04969-123">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="04969-124">-CurrentUser: 현재 사용자에 게 할당 된 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="04969-124">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="04969-125">기본값은 LocalMachine입니다.</span><span class="sxs-lookup"><span data-stu-id="04969-125">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="04969-126">열려는 X.509 인증서 저장소의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="04969-126">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="04969-127">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="04969-127">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="04969-128">AddressBook 다른 사용자를 위한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="04969-128">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="04969-129">-   AuthRoot: 타사 Ca (인증 기관) 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="04969-129">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="04969-130">CertificationAuthority 중간 Ca (인증 기관) 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="04969-130">-   CertificationAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="04969-131">허용 해지 된 인증서용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="04969-131">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="04969-132">결재 개인 인증서용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="04969-132">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="04969-133">루트가 신뢰할 수 있는 루트 Ca (인증 기관) 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="04969-133">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="04969-134">TrustedPeople 직접 신뢰할 수 있는 사람 및 리소스용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="04969-134">-   TrustedPeople: Certificate store for directly trusted people and resources.</span></span><br /><span data-ttu-id="04969-135">TrustedPublisher 직접 신뢰할 수 있는 게시자 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="04969-135">-   TrustedPublisher: Certificate store for directly trusted publishers.</span></span><br /><br /> <span data-ttu-id="04969-136">기본값은 My입니다.</span><span class="sxs-lookup"><span data-stu-id="04969-136">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="04969-137">실행할 X.509 검색의 유형을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="04969-137">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="04969-138">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="04969-138">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="04969-139">-   FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="04969-139">-   FindByThumbPrint</span></span><br /><span data-ttu-id="04969-140">-   FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="04969-140">-   FindBySubjectName</span></span><br /><span data-ttu-id="04969-141">-   FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="04969-141">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="04969-142">-   FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="04969-142">-   FindByIssuerName</span></span><br /><span data-ttu-id="04969-143">-   FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="04969-143">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="04969-144">-   FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="04969-144">-   FindBySerialNumber</span></span><br /><span data-ttu-id="04969-145">-   FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="04969-145">-   FindByTimeValid</span></span><br /><span data-ttu-id="04969-146">-   FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="04969-146">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="04969-147">-   FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="04969-147">-   FindByTemplateName</span></span><br /><span data-ttu-id="04969-148">-   FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="04969-148">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="04969-149">-   FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="04969-149">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="04969-150">-   FindByExtension</span><span class="sxs-lookup"><span data-stu-id="04969-150">-   FindByExtension</span></span><br /><span data-ttu-id="04969-151">-   FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="04969-151">-   FindByKeyUsage</span></span><br /><span data-ttu-id="04969-152">-   FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="04969-152">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="04969-153">`findValue` 특성에 포함된 형식은 지정된 X509FindType에 대한 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04969-153">The type contained in the `findValue` attribute must satisfy the requirements of the specified X509FindType.</span></span><br /><br /> <span data-ttu-id="04969-154">기본값은 FindBySubjectDistinguishedName입니다.</span><span class="sxs-lookup"><span data-stu-id="04969-154">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="04969-155">자식 요소</span><span class="sxs-lookup"><span data-stu-id="04969-155">Child Elements</span></span>  
 <span data-ttu-id="04969-156">없음</span><span class="sxs-lookup"><span data-stu-id="04969-156">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="04969-157">부모 요소</span><span class="sxs-lookup"><span data-stu-id="04969-157">Parent Elements</span></span>  
  
|<span data-ttu-id="04969-158">요소</span><span class="sxs-lookup"><span data-stu-id="04969-158">Element</span></span>|<span data-ttu-id="04969-159">설명</span><span class="sxs-lookup"><span data-stu-id="04969-159">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="04969-160">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="04969-160">\<clientCertificate></span></span>](clientcertificate-of-servicecredentials.md)||  
  
## <a name="remarks"></a><span data-ttu-id="04969-161">설명</span><span class="sxs-lookup"><span data-stu-id="04969-161">Remarks</span></span>  
 <span data-ttu-id="04969-162">서비스가 클라이언트와 안전하게 통신하기 위해 클라이언트의 인증서가 필요한 경우 `<certificate>` 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="04969-162">The `<certificate>` element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="04969-163">이는 양방향 통신 패턴을 사용하는 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="04969-163">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="04969-164">대부분의 일반적인 요청/응답 패턴의 경우 클라이언트는 요청 시 서비스가 클라이언트에게 해당 응답을 암호화 및 서명하는 데 사용하는 인증서를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="04969-164">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="04969-165">그러나 이중 통신 패턴에서는 서비스에 클라이언트의 요청이 없으므로 클라이언트에게 보내는 메시지 보안을 위해 클라이언트의 인증서가 사전에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="04969-165">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="04969-166">따라서 클라이언트 인증서를 out-of-band 협상 방식으로 가져와서 이 요소를 사용하여 인증서를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04969-166">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="04969-167">이중 서비스 [에 대 한 자세한 내용은 방법: 이중 계약](../../../wcf/feature-details/how-to-create-a-duplex-contract.md)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="04969-167">For more information about duplex services, see [How to: Create a Duplex Contract](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="04969-168">예제</span><span class="sxs-lookup"><span data-stu-id="04969-168">Example</span></span>  
 <span data-ttu-id="04969-169">다음 코드에서는 적절한 X.509 인증서와 `<authentication>` 요소의 사용자 지정 유효성 검사 형식을 찾는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="04969-169">The following code specifies how to find an appropriate X.509 certificate and a custom validation type in the `<authentication>` element.</span></span>  
  
```xml  
<serviceBehaviors>
  <behavior name="myServiceBehavior">
    <clientCertificate>
      <certificate findValue="www.cohowinery.com"
                   storeLocation="CurrentUser"
                   storeName="TrustedPeople"
                   x509FindType="FindByIssuerName" />
      <authentication customCertificateValidatorType="MyTypes.Coho"
                      certificateValidationMode="Custom"
                      revocationMode="Offline"
                      includeWindowsGroups="false"
                      mapClientCertificateToWindowsAccount="true" />
    </clientCertificate>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="04969-170">참고자료</span><span class="sxs-lookup"><span data-stu-id="04969-170">See also</span></span>

- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509ClientCertificateCredentialsElement>
- [<span data-ttu-id="04969-171">보안 동작</span><span class="sxs-lookup"><span data-stu-id="04969-171">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="04969-172">방법: 사용자 지정 인증서 유효성 검사기를 채택 하는 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="04969-172">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [<span data-ttu-id="04969-173">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="04969-173">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
