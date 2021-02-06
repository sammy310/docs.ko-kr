---
description: '다음에 대 한 자세한 정보: <certificate> <clientCertificate> 요소'
title: <certificate> of <clientCertificate> 요소
ms.date: 03/30/2017
ms.assetid: 00297efb-a7f2-4e03-bc2b-943d545610fc
ms.openlocfilehash: a677c04055016c77794dd99a8c237b5eb6c13f5f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639096"
---
# <a name="certificate-of-clientcertificate-element"></a><span data-ttu-id="ff7cd-103">\<certificate> of \<clientCertificate> 요소</span><span class="sxs-lookup"><span data-stu-id="ff7cd-103">\<certificate> of \<clientCertificate> Element</span></span>

<span data-ttu-id="ff7cd-104">메시지 서명 및 암호화에 사용되는 X.509 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ff7cd-104">Specifies an X.509 certificate used to sign and encrypt messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCertificate>**](clientcertificate-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**  
  
## <a name="syntax"></a><span data-ttu-id="ff7cd-105">구문</span><span class="sxs-lookup"><span data-stu-id="ff7cd-105">Syntax</span></span>  
  
```xml  
<certificate findValue="String"
             storeLocation = "CurrentUser/LocalMachine"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ff7cd-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ff7cd-106">Attributes and Elements</span></span>  

 <span data-ttu-id="ff7cd-107">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ff7cd-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ff7cd-108">특성</span><span class="sxs-lookup"><span data-stu-id="ff7cd-108">Attributes</span></span>  
  
|<span data-ttu-id="ff7cd-109">attribute</span><span class="sxs-lookup"><span data-stu-id="ff7cd-109">Attribute</span></span>|<span data-ttu-id="ff7cd-110">설명</span><span class="sxs-lookup"><span data-stu-id="ff7cd-110">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="ff7cd-111">X.509 인증서 저장소에서 검색할 값을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ff7cd-111">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="ff7cd-112">이 특성에 포함된 형식은 지정된 X509FindType에 대한 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff7cd-112">The type contained in the attribute must satisfy the requirements of the specified X509FindType.</span></span> <span data-ttu-id="ff7cd-113">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ff7cd-113">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="ff7cd-114">클라이언트가 서버 인증서의 유효성을 검사하는 데 사용하는 X.509 인증서 저장소 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ff7cd-114">Specifies the location of the X.509 certificate store that the client uses to validate the server’s certificate against.</span></span> <span data-ttu-id="ff7cd-115">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ff7cd-115">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="ff7cd-116">-LocalMachine: 로컬 컴퓨터에 할당 된 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="ff7cd-116">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="ff7cd-117">-CurrentUser: 현재 사용자에 게 할당 된 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="ff7cd-117">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="ff7cd-118">기본값은 LocalMachine입니다.</span><span class="sxs-lookup"><span data-stu-id="ff7cd-118">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="ff7cd-119">열려는 X.509 인증서 저장소의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ff7cd-119">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="ff7cd-120">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ff7cd-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="ff7cd-121">-AddressBook: 다른 사용자에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="ff7cd-121">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="ff7cd-122">-AuthRoot: 타사 Ca (인증 기관) 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="ff7cd-122">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="ff7cd-123">-CertificationAuthority: 중간 Ca (인증 기관) 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="ff7cd-123">-   CertificationAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="ff7cd-124">-허용 안 함: 해지 된 인증서의 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="ff7cd-124">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="ff7cd-125">-My: 개인 인증서용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="ff7cd-125">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="ff7cd-126">-Root: 신뢰할 수 있는 루트 Ca (인증 기관) 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="ff7cd-126">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="ff7cd-127">-개인 사용자: 직접 신뢰할 수 있는 사용자 및 리소스에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="ff7cd-127">-   TrustedPeople: Certificate store for directly trusted people and resources.</span></span><br /><span data-ttu-id="ff7cd-128">-신뢰할 수 있는 게시자: 직접 신뢰할 수 있는 게시자 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="ff7cd-128">-   TrustedPublisher: Certificate store for directly trusted publishers.</span></span><br /><br /> <span data-ttu-id="ff7cd-129">기본값은 My입니다.</span><span class="sxs-lookup"><span data-stu-id="ff7cd-129">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="ff7cd-130">실행할 X.509 검색의 유형을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ff7cd-130">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="ff7cd-131">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ff7cd-131">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="ff7cd-132">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="ff7cd-132">-   FindByThumbPrint</span></span><br /><span data-ttu-id="ff7cd-133">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="ff7cd-133">-   FindBySubjectName</span></span><br /><span data-ttu-id="ff7cd-134">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="ff7cd-134">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="ff7cd-135">- FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="ff7cd-135">-   FindByIssuerName</span></span><br /><span data-ttu-id="ff7cd-136">- FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="ff7cd-136">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="ff7cd-137">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="ff7cd-137">-   FindBySerialNumber</span></span><br /><span data-ttu-id="ff7cd-138">- FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="ff7cd-138">-   FindByTimeValid</span></span><br /><span data-ttu-id="ff7cd-139">- FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="ff7cd-139">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="ff7cd-140">- FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="ff7cd-140">-   FindByTemplateName</span></span><br /><span data-ttu-id="ff7cd-141">- FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="ff7cd-141">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="ff7cd-142">- FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="ff7cd-142">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="ff7cd-143">- FindByExtension</span><span class="sxs-lookup"><span data-stu-id="ff7cd-143">-   FindByExtension</span></span><br /><span data-ttu-id="ff7cd-144">- FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="ff7cd-144">-   FindByKeyUsage</span></span><br /><span data-ttu-id="ff7cd-145">- FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="ff7cd-145">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="ff7cd-146">`findValue` 특성에 포함된 형식은 지정된 X509FindType에 대한 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff7cd-146">The type contained in the `findValue` attribute must satisfy the requirements of the specified X509FindType.</span></span><br /><br /> <span data-ttu-id="ff7cd-147">기본값은 FindBySubjectDistinguishedName입니다.</span><span class="sxs-lookup"><span data-stu-id="ff7cd-147">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ff7cd-148">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ff7cd-148">Child Elements</span></span>  

 <span data-ttu-id="ff7cd-149">없음</span><span class="sxs-lookup"><span data-stu-id="ff7cd-149">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ff7cd-150">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ff7cd-150">Parent Elements</span></span>  
  
|<span data-ttu-id="ff7cd-151">요소</span><span class="sxs-lookup"><span data-stu-id="ff7cd-151">Element</span></span>|<span data-ttu-id="ff7cd-152">Description</span><span class="sxs-lookup"><span data-stu-id="ff7cd-152">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCertificate>](clientcertificate-of-servicecredentials.md)||  
  
## <a name="remarks"></a><span data-ttu-id="ff7cd-153">설명</span><span class="sxs-lookup"><span data-stu-id="ff7cd-153">Remarks</span></span>  

 <span data-ttu-id="ff7cd-154">서비스가 클라이언트와 안전하게 통신하기 위해 클라이언트의 인증서가 필요한 경우 `<certificate>` 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ff7cd-154">The `<certificate>` element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="ff7cd-155">이는 양방향 통신 패턴을 사용하는 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ff7cd-155">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="ff7cd-156">대부분의 일반적인 요청/응답 패턴의 경우 클라이언트는 요청 시 서비스가 클라이언트에게 해당 응답을 암호화 및 서명하는 데 사용하는 인증서를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ff7cd-156">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="ff7cd-157">그러나 이중 통신 패턴에서는 서비스에 클라이언트의 요청이 없으므로 클라이언트에게 보내는 메시지 보안을 위해 클라이언트의 인증서가 사전에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ff7cd-157">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="ff7cd-158">따라서 클라이언트 인증서를 out-of-band 협상 방식으로 가져와서 이 요소를 사용하여 인증서를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff7cd-158">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="ff7cd-159">이중 서비스에 대 한 자세한 내용은 [방법: 이중 계약 만들기](../../../wcf/feature-details/how-to-create-a-duplex-contract.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ff7cd-159">For more information about duplex services, see [How to: Create a Duplex Contract](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff7cd-160">예제</span><span class="sxs-lookup"><span data-stu-id="ff7cd-160">Example</span></span>  

 <span data-ttu-id="ff7cd-161">다음 코드에서는 적절한 X.509 인증서와 `<authentication>` 요소의 사용자 지정 유효성 검사 형식을 찾는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ff7cd-161">The following code specifies how to find an appropriate X.509 certificate and a custom validation type in the `<authentication>` element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ff7cd-162">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ff7cd-162">See also</span></span>

- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509ClientCertificateCredentialsElement>
- [<span data-ttu-id="ff7cd-163">보안 동작</span><span class="sxs-lookup"><span data-stu-id="ff7cd-163">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="ff7cd-164">방법: 사용자 지정 인증서 유효성 검사기를 사용하는 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="ff7cd-164">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [<span data-ttu-id="ff7cd-165">인증서 사용</span><span class="sxs-lookup"><span data-stu-id="ff7cd-165">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
