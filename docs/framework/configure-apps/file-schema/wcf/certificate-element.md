---
title: <certificate> 요소
ms.date: 03/30/2017
ms.assetid: 9b3d9233-ef35-477a-bf5d-efd1e80a52f4
ms.openlocfilehash: e28e7d16073a56f3b6126439644bfff86c9af18b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400550"
---
# <a name="certificate-element"></a><span data-ttu-id="e9d1e-102">\<certificate > 요소</span><span class="sxs-lookup"><span data-stu-id="e9d1e-102">\<certificate> Element</span></span>
<span data-ttu-id="e9d1e-103">피어 투 피어 클라이언트의 메시지를 서명 및 암호화하는 데 사용하는 X.509 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e9d1e-103">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span>  
  
<span data-ttu-id="e9d1e-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e9d1e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e9d1e-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e9d1e-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e9d1e-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e9d1e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="e9d1e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e9d1e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="e9d1e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e9d1e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="e9d1e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="e9d1e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="e9d1e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<피어 >** ](peer-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="e9d1e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)</span></span>\
<span data-ttu-id="e9d1e-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<인증서 >**</span><span class="sxs-lookup"><span data-stu-id="e9d1e-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9d1e-112">구문</span><span class="sxs-lookup"><span data-stu-id="e9d1e-112">Syntax</span></span>  
  
```xml  
<certificate findValue="String"
             storeLocation="LocalMachine/CurrentUser"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9d1e-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e9d1e-113">Attributes and Elements</span></span>  
 <span data-ttu-id="e9d1e-114">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e9d1e-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9d1e-115">특성</span><span class="sxs-lookup"><span data-stu-id="e9d1e-115">Attributes</span></span>  
  
|<span data-ttu-id="e9d1e-116">특성</span><span class="sxs-lookup"><span data-stu-id="e9d1e-116">Attribute</span></span>|<span data-ttu-id="e9d1e-117">설명</span><span class="sxs-lookup"><span data-stu-id="e9d1e-117">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="e9d1e-118">X.509 인증서 저장소에서 검색할 값을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="e9d1e-118">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="e9d1e-119">이 특성에 포함된 형식은 지정한 `x509FindType`의 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9d1e-119">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="e9d1e-120">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="e9d1e-120">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="e9d1e-121">클라이언트가 피어 인증서의 유효성을 검사하는 데 사용하는 X.509 인증서 저장소의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e9d1e-121">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="e9d1e-122">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e9d1e-122">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e9d1e-123">-LocalMachine: 로컬 컴퓨터에 할당 된 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="e9d1e-123">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="e9d1e-124">-CurrentUser: 현재 사용자에 게 할당 된 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="e9d1e-124">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="e9d1e-125">기본값은 LocalMachine입니다.</span><span class="sxs-lookup"><span data-stu-id="e9d1e-125">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="e9d1e-126">열려는 X.509 인증서 저장소의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e9d1e-126">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="e9d1e-127">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e9d1e-127">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e9d1e-128">AddressBook 다른 사용자를 위한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="e9d1e-128">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="e9d1e-129">-   AuthRoot: 타사 Ca (인증 기관) 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="e9d1e-129">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="e9d1e-130">-   CertificateAuthority: 중간 Ca (인증 기관) 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="e9d1e-130">-   CertificateAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="e9d1e-131">허용 해지 된 인증서용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="e9d1e-131">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="e9d1e-132">결재 개인 인증서용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="e9d1e-132">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="e9d1e-133">루트가 신뢰할 수 있는 루트 Ca (인증 기관) 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="e9d1e-133">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="e9d1e-134">TrustedPeople 직접 신뢰할 수 있는 사람 및 리소스용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="e9d1e-134">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="e9d1e-135">TrustedPublisher 직접 신뢰할 수 있는 게시자 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="e9d1e-135">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="e9d1e-136">기본값은 My입니다.</span><span class="sxs-lookup"><span data-stu-id="e9d1e-136">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="e9d1e-137">실행할 X.509 검색의 유형을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e9d1e-137">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="e9d1e-138">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e9d1e-138">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e9d1e-139">-   FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="e9d1e-139">-   FindByThumbPrint</span></span><br /><span data-ttu-id="e9d1e-140">-   FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="e9d1e-140">-   FindBySubjectName</span></span><br /><span data-ttu-id="e9d1e-141">-   FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="e9d1e-141">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="e9d1e-142">-   FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="e9d1e-142">-   FindByIssuerName</span></span><br /><span data-ttu-id="e9d1e-143">-   FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="e9d1e-143">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="e9d1e-144">-   FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="e9d1e-144">-   FindBySerialNumber</span></span><br /><span data-ttu-id="e9d1e-145">-   FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="e9d1e-145">-   FindByTimeValid</span></span><br /><span data-ttu-id="e9d1e-146">-   FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="e9d1e-146">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="e9d1e-147">-   FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="e9d1e-147">-   FindByTemplateName</span></span><br /><span data-ttu-id="e9d1e-148">-   FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="e9d1e-148">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="e9d1e-149">-   FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="e9d1e-149">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="e9d1e-150">-   FindByExtension</span><span class="sxs-lookup"><span data-stu-id="e9d1e-150">-   FindByExtension</span></span><br /><span data-ttu-id="e9d1e-151">-   FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="e9d1e-151">-   FindByKeyUsage</span></span><br /><span data-ttu-id="e9d1e-152">-   FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="e9d1e-152">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="e9d1e-153">`findValue` 특성에 포함된 형식은 지정한 `X509FindType`의 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9d1e-153">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="e9d1e-154">기본값은 FindBySubjectDistinguishedName입니다.</span><span class="sxs-lookup"><span data-stu-id="e9d1e-154">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e9d1e-155">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e9d1e-155">Child Elements</span></span>  
 <span data-ttu-id="e9d1e-156">없음</span><span class="sxs-lookup"><span data-stu-id="e9d1e-156">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e9d1e-157">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e9d1e-157">Parent Elements</span></span>  
  
|<span data-ttu-id="e9d1e-158">요소</span><span class="sxs-lookup"><span data-stu-id="e9d1e-158">Element</span></span>|<span data-ttu-id="e9d1e-159">Description</span><span class="sxs-lookup"><span data-stu-id="e9d1e-159">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e9d1e-160">\<peer></span><span class="sxs-lookup"><span data-stu-id="e9d1e-160">\<peer></span></span>](peer-of-clientcredentials-element.md)|<span data-ttu-id="e9d1e-161">피어 투 피어 클라이언트를 인증할 때 사용하는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e9d1e-161">Specifies credentials used when authenticating peer-to-peer clients.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9d1e-162">설명</span><span class="sxs-lookup"><span data-stu-id="e9d1e-162">Remarks</span></span>  
 <span data-ttu-id="e9d1e-163">이 구성 요소는 피어 메시에서 환경을 인증할 때 사용되는 X509Certificate2 인스턴스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e9d1e-163">This configuration element contains a X509Certificate2 instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="e9d1e-164">피어 투 피어 프로그래밍에 대 한 자세한 내용은 [피어 투 피어 네트워킹](../../../wcf/feature-details/peer-to-peer-networking.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e9d1e-164">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9d1e-165">예제</span><span class="sxs-lookup"><span data-stu-id="e9d1e-165">Example</span></span>  
 <span data-ttu-id="e9d1e-166">다음 코드에서는 피어 투 피어 시나리오에서 사용된 인증서를 찾는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e9d1e-166">The following code specifies how to find the certificate used in a peer-to-peer scenario.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <peer>
          <certificate findValue="www.contoso.com"
                       storeLocation="LocalMachine"
                       x509FindType="FindByIssuerName" />
        </peer>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="e9d1e-167">참고자료</span><span class="sxs-lookup"><span data-stu-id="e9d1e-167">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>
- <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>
- [<span data-ttu-id="e9d1e-168">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="e9d1e-168">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="e9d1e-169">피어 투 피어 네트워킹</span><span class="sxs-lookup"><span data-stu-id="e9d1e-169">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="e9d1e-170">[피어 채널 메시지 인증](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="e9d1e-170">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="e9d1e-171">[피어 채널 사용자 지정 인증](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="e9d1e-171">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="e9d1e-172">피어 채널 애플리케이션 보안</span><span class="sxs-lookup"><span data-stu-id="e9d1e-172">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
