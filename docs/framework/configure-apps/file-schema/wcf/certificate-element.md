---
description: '다음에 대 한 자세한 정보: <certificate> 요소'
title: <certificate> 요소
ms.date: 03/30/2017
ms.assetid: 9b3d9233-ef35-477a-bf5d-efd1e80a52f4
ms.openlocfilehash: 3f67435d86f19f81c1f6fe1fe2a9a8afbef69e53
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639135"
---
# <a name="certificate-element"></a><span data-ttu-id="85989-103">\<certificate> 요소</span><span class="sxs-lookup"><span data-stu-id="85989-103">\<certificate> Element</span></span>

<span data-ttu-id="85989-104">피어 투 피어 클라이언트의 메시지를 서명 및 암호화하는 데 사용하는 X.509 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="85989-104">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**  
  
## <a name="syntax"></a><span data-ttu-id="85989-105">구문</span><span class="sxs-lookup"><span data-stu-id="85989-105">Syntax</span></span>  
  
```xml  
<certificate findValue="String"
             storeLocation="LocalMachine/CurrentUser"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="85989-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="85989-106">Attributes and Elements</span></span>  

 <span data-ttu-id="85989-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="85989-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="85989-108">특성</span><span class="sxs-lookup"><span data-stu-id="85989-108">Attributes</span></span>  
  
|<span data-ttu-id="85989-109">attribute</span><span class="sxs-lookup"><span data-stu-id="85989-109">Attribute</span></span>|<span data-ttu-id="85989-110">설명</span><span class="sxs-lookup"><span data-stu-id="85989-110">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="85989-111">X.509 인증서 저장소에서 검색할 값을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="85989-111">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="85989-112">이 특성에 포함된 형식은 지정한 `x509FindType`의 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85989-112">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="85989-113">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="85989-113">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="85989-114">클라이언트가 피어 인증서의 유효성을 검사하는 데 사용하는 X.509 인증서 저장소의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="85989-114">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="85989-115">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="85989-115">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="85989-116">-LocalMachine: 로컬 컴퓨터에 할당 된 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="85989-116">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="85989-117">-CurrentUser: 현재 사용자에 게 할당 된 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="85989-117">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="85989-118">기본값은 LocalMachine입니다.</span><span class="sxs-lookup"><span data-stu-id="85989-118">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="85989-119">열려는 X.509 인증서 저장소의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="85989-119">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="85989-120">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="85989-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="85989-121">-AddressBook: 다른 사용자에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="85989-121">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="85989-122">-AuthRoot: 타사 Ca (인증 기관) 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="85989-122">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="85989-123">-CertificateAuthority: 중개 Ca (인증 기관) 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="85989-123">-   CertificateAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="85989-124">-허용 안 함: 해지 된 인증서의 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="85989-124">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="85989-125">-My: 개인 인증서용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="85989-125">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="85989-126">-Root: 신뢰할 수 있는 루트 Ca (인증 기관) 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="85989-126">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="85989-127">-개인 사용자: 직접 신뢰할 수 있는 사용자 및 리소스에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="85989-127">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="85989-128">-신뢰할 수 있는 게시자: 직접 신뢰할 수 있는 게시자 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="85989-128">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="85989-129">기본값은 My입니다.</span><span class="sxs-lookup"><span data-stu-id="85989-129">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="85989-130">실행할 X.509 검색의 유형을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="85989-130">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="85989-131">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="85989-131">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="85989-132">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="85989-132">-   FindByThumbPrint</span></span><br /><span data-ttu-id="85989-133">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="85989-133">-   FindBySubjectName</span></span><br /><span data-ttu-id="85989-134">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="85989-134">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="85989-135">- FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="85989-135">-   FindByIssuerName</span></span><br /><span data-ttu-id="85989-136">- FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="85989-136">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="85989-137">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="85989-137">-   FindBySerialNumber</span></span><br /><span data-ttu-id="85989-138">- FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="85989-138">-   FindByTimeValid</span></span><br /><span data-ttu-id="85989-139">- FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="85989-139">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="85989-140">- FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="85989-140">-   FindByTemplateName</span></span><br /><span data-ttu-id="85989-141">- FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="85989-141">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="85989-142">- FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="85989-142">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="85989-143">- FindByExtension</span><span class="sxs-lookup"><span data-stu-id="85989-143">-   FindByExtension</span></span><br /><span data-ttu-id="85989-144">- FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="85989-144">-   FindByKeyUsage</span></span><br /><span data-ttu-id="85989-145">- FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="85989-145">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="85989-146">`findValue` 특성에 포함된 형식은 지정한 `X509FindType`의 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85989-146">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="85989-147">기본값은 FindBySubjectDistinguishedName입니다.</span><span class="sxs-lookup"><span data-stu-id="85989-147">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="85989-148">자식 요소</span><span class="sxs-lookup"><span data-stu-id="85989-148">Child Elements</span></span>  

 <span data-ttu-id="85989-149">없음</span><span class="sxs-lookup"><span data-stu-id="85989-149">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="85989-150">부모 요소</span><span class="sxs-lookup"><span data-stu-id="85989-150">Parent Elements</span></span>  
  
|<span data-ttu-id="85989-151">요소</span><span class="sxs-lookup"><span data-stu-id="85989-151">Element</span></span>|<span data-ttu-id="85989-152">설명</span><span class="sxs-lookup"><span data-stu-id="85989-152">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-clientcredentials-element.md)|<span data-ttu-id="85989-153">피어 투 피어 클라이언트를 인증할 때 사용하는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="85989-153">Specifies credentials used when authenticating peer-to-peer clients.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85989-154">설명</span><span class="sxs-lookup"><span data-stu-id="85989-154">Remarks</span></span>  

 <span data-ttu-id="85989-155">이 구성 요소는 피어 메시에서 환경을 인증할 때 사용되는 X509Certificate2 인스턴스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="85989-155">This configuration element contains a X509Certificate2 instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="85989-156">피어 투 피어 프로그래밍에 대 한 자세한 내용은 [피어 투 피어 네트워킹](../../../wcf/feature-details/peer-to-peer-networking.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="85989-156">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="85989-157">예제</span><span class="sxs-lookup"><span data-stu-id="85989-157">Example</span></span>  

 <span data-ttu-id="85989-158">다음 코드에서는 피어 투 피어 시나리오에서 사용된 인증서를 찾는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="85989-158">The following code specifies how to find the certificate used in a peer-to-peer scenario.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="85989-159">참고 항목</span><span class="sxs-lookup"><span data-stu-id="85989-159">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>
- <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>
- [<span data-ttu-id="85989-160">인증서 사용</span><span class="sxs-lookup"><span data-stu-id="85989-160">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="85989-161">피어 투 피어 네트워킹</span><span class="sxs-lookup"><span data-stu-id="85989-161">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="85989-162">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="85989-162">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="85989-163">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="85989-163">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="85989-164">피어 채널 애플리케이션 보안</span><span class="sxs-lookup"><span data-stu-id="85989-164">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
