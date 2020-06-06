---
title: <certificate>of <clientCertificate> 요소
ms.date: 03/30/2017
ms.assetid: 00297efb-a7f2-4e03-bc2b-943d545610fc
ms.openlocfilehash: d0c4ef9d3657d2dfa787feb3576beda09d1997a3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400539"
---
# <a name="certificate-of-clientcertificate-element"></a><span data-ttu-id="998c2-102">\<certificate>of \<clientCertificate> 요소</span><span class="sxs-lookup"><span data-stu-id="998c2-102">\<certificate> of \<clientCertificate> Element</span></span>
<span data-ttu-id="998c2-103">메시지 서명 및 암호화에 사용되는 X.509 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="998c2-103">Specifies an X.509 certificate used to sign and encrypt messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCertificate>**](clientcertificate-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**  
  
## <a name="syntax"></a><span data-ttu-id="998c2-104">구문</span><span class="sxs-lookup"><span data-stu-id="998c2-104">Syntax</span></span>  
  
```xml  
<certificate findValue="String"
             storeLocation = "CurrentUser/LocalMachine"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="998c2-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="998c2-105">Attributes and Elements</span></span>  
 <span data-ttu-id="998c2-106">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="998c2-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="998c2-107">특성</span><span class="sxs-lookup"><span data-stu-id="998c2-107">Attributes</span></span>  
  
|<span data-ttu-id="998c2-108">attribute</span><span class="sxs-lookup"><span data-stu-id="998c2-108">Attribute</span></span>|<span data-ttu-id="998c2-109">Description</span><span class="sxs-lookup"><span data-stu-id="998c2-109">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="998c2-110">X.509 인증서 저장소에서 검색할 값을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="998c2-110">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="998c2-111">이 특성에 포함된 형식은 지정된 X509FindType에 대한 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="998c2-111">The type contained in the attribute must satisfy the requirements of the specified X509FindType.</span></span> <span data-ttu-id="998c2-112">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="998c2-112">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="998c2-113">클라이언트가 서버 인증서의 유효성을 검사하는 데 사용하는 X.509 인증서 저장소 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="998c2-113">Specifies the location of the X.509 certificate store that the client uses to validate the server’s certificate against.</span></span> <span data-ttu-id="998c2-114">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="998c2-114">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="998c2-115">-LocalMachine: 로컬 컴퓨터에 할당 된 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="998c2-115">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="998c2-116">-CurrentUser: 현재 사용자에 게 할당 된 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="998c2-116">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="998c2-117">기본값은 LocalMachine입니다.</span><span class="sxs-lookup"><span data-stu-id="998c2-117">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="998c2-118">열려는 X.509 인증서 저장소의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="998c2-118">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="998c2-119">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="998c2-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="998c2-120">-AddressBook: 다른 사용자에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="998c2-120">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="998c2-121">-AuthRoot: 타사 Ca (인증 기관) 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="998c2-121">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="998c2-122">-CertificationAuthority: 중간 Ca (인증 기관) 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="998c2-122">-   CertificationAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="998c2-123">-허용 안 함: 해지 된 인증서의 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="998c2-123">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="998c2-124">-My: 개인 인증서용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="998c2-124">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="998c2-125">-Root: 신뢰할 수 있는 루트 Ca (인증 기관) 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="998c2-125">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="998c2-126">-개인 사용자: 직접 신뢰할 수 있는 사용자 및 리소스에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="998c2-126">-   TrustedPeople: Certificate store for directly trusted people and resources.</span></span><br /><span data-ttu-id="998c2-127">-신뢰할 수 있는 게시자: 직접 신뢰할 수 있는 게시자 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="998c2-127">-   TrustedPublisher: Certificate store for directly trusted publishers.</span></span><br /><br /> <span data-ttu-id="998c2-128">기본값은 My입니다.</span><span class="sxs-lookup"><span data-stu-id="998c2-128">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="998c2-129">실행할 X.509 검색의 유형을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="998c2-129">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="998c2-130">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="998c2-130">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="998c2-131">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="998c2-131">-   FindByThumbPrint</span></span><br /><span data-ttu-id="998c2-132">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="998c2-132">-   FindBySubjectName</span></span><br /><span data-ttu-id="998c2-133">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="998c2-133">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="998c2-134">- FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="998c2-134">-   FindByIssuerName</span></span><br /><span data-ttu-id="998c2-135">- FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="998c2-135">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="998c2-136">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="998c2-136">-   FindBySerialNumber</span></span><br /><span data-ttu-id="998c2-137">- FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="998c2-137">-   FindByTimeValid</span></span><br /><span data-ttu-id="998c2-138">- FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="998c2-138">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="998c2-139">- FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="998c2-139">-   FindByTemplateName</span></span><br /><span data-ttu-id="998c2-140">- FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="998c2-140">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="998c2-141">- FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="998c2-141">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="998c2-142">- FindByExtension</span><span class="sxs-lookup"><span data-stu-id="998c2-142">-   FindByExtension</span></span><br /><span data-ttu-id="998c2-143">- FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="998c2-143">-   FindByKeyUsage</span></span><br /><span data-ttu-id="998c2-144">- FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="998c2-144">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="998c2-145">`findValue` 특성에 포함된 형식은 지정된 X509FindType에 대한 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="998c2-145">The type contained in the `findValue` attribute must satisfy the requirements of the specified X509FindType.</span></span><br /><br /> <span data-ttu-id="998c2-146">기본값은 FindBySubjectDistinguishedName입니다.</span><span class="sxs-lookup"><span data-stu-id="998c2-146">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="998c2-147">자식 요소</span><span class="sxs-lookup"><span data-stu-id="998c2-147">Child Elements</span></span>  
 <span data-ttu-id="998c2-148">없음</span><span class="sxs-lookup"><span data-stu-id="998c2-148">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="998c2-149">부모 요소</span><span class="sxs-lookup"><span data-stu-id="998c2-149">Parent Elements</span></span>  
  
|<span data-ttu-id="998c2-150">요소</span><span class="sxs-lookup"><span data-stu-id="998c2-150">Element</span></span>|<span data-ttu-id="998c2-151">Description</span><span class="sxs-lookup"><span data-stu-id="998c2-151">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCertificate>](clientcertificate-of-servicecredentials.md)||  
  
## <a name="remarks"></a><span data-ttu-id="998c2-152">설명</span><span class="sxs-lookup"><span data-stu-id="998c2-152">Remarks</span></span>  
 <span data-ttu-id="998c2-153">서비스가 클라이언트와 안전하게 통신하기 위해 클라이언트의 인증서가 필요한 경우 `<certificate>` 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="998c2-153">The `<certificate>` element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="998c2-154">이는 양방향 통신 패턴을 사용하는 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="998c2-154">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="998c2-155">대부분의 일반적인 요청/응답 패턴의 경우 클라이언트는 요청 시 서비스가 클라이언트에게 해당 응답을 암호화 및 서명하는 데 사용하는 인증서를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="998c2-155">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="998c2-156">그러나 이중 통신 패턴에서는 서비스에 클라이언트의 요청이 없으므로 클라이언트에게 보내는 메시지 보안을 위해 클라이언트의 인증서가 사전에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="998c2-156">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="998c2-157">따라서 클라이언트 인증서를 out-of-band 협상 방식으로 가져와서 이 요소를 사용하여 인증서를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="998c2-157">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="998c2-158">이중 서비스에 대 한 자세한 내용은 [방법: 이중 계약 만들기](../../../wcf/feature-details/how-to-create-a-duplex-contract.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="998c2-158">For more information about duplex services, see [How to: Create a Duplex Contract](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="998c2-159">예제</span><span class="sxs-lookup"><span data-stu-id="998c2-159">Example</span></span>  
 <span data-ttu-id="998c2-160">다음 코드에서는 적절한 X.509 인증서와 `<authentication>` 요소의 사용자 지정 유효성 검사 형식을 찾는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="998c2-160">The following code specifies how to find an appropriate X.509 certificate and a custom validation type in the `<authentication>` element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="998c2-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="998c2-161">See also</span></span>

- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509ClientCertificateCredentialsElement>
- [<span data-ttu-id="998c2-162">보안 동작</span><span class="sxs-lookup"><span data-stu-id="998c2-162">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="998c2-163">방법: 사용자 지정 인증서 유효성 검사기를 사용하는 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="998c2-163">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [<span data-ttu-id="998c2-164">인증서 사용</span><span class="sxs-lookup"><span data-stu-id="998c2-164">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
