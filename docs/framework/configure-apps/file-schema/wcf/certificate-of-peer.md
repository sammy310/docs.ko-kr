---
title: <peer>의 <certificate>
ms.date: 03/30/2017
ms.assetid: 48b69142-c957-4305-a042-c9d0c9a55c0e
ms.openlocfilehash: 8ec839df02af4a01d31192eebc96e4c5e58313e9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151118"
---
# <a name="certificate-of-peer"></a><span data-ttu-id="39c8c-102">\<peer>의 \<certificate></span><span class="sxs-lookup"><span data-stu-id="39c8c-102">\<certificate> of \<peer></span></span>

<span data-ttu-id="39c8c-103">피어에서 사용하는 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="39c8c-103">Specifies a certificate used by a peer.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**  
  
## <a name="syntax"></a><span data-ttu-id="39c8c-104">구문</span><span class="sxs-lookup"><span data-stu-id="39c8c-104">Syntax</span></span>  
  
```xml  
<certificate findValue = "String"
             storeLocation = "CurrentUser/LocalMachine"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="39c8c-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="39c8c-105">Attributes and Elements</span></span>  

 <span data-ttu-id="39c8c-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="39c8c-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="39c8c-107">특성</span><span class="sxs-lookup"><span data-stu-id="39c8c-107">Attributes</span></span>  
  
|<span data-ttu-id="39c8c-108">attribute</span><span class="sxs-lookup"><span data-stu-id="39c8c-108">Attribute</span></span>|<span data-ttu-id="39c8c-109">설명</span><span class="sxs-lookup"><span data-stu-id="39c8c-109">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="39c8c-110">X.509 인증서 저장소에서 검색할 값을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="39c8c-110">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="39c8c-111">이 특성에 포함된 형식은 지정한 `x509FindType`의 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39c8c-111">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="39c8c-112">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="39c8c-112">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="39c8c-113">클라이언트가 피어 인증서의 유효성을 검사하는 데 사용하는 X.509 인증서 저장소의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="39c8c-113">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="39c8c-114">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="39c8c-114">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="39c8c-115">-LocalMachine: 로컬 컴퓨터에 할당 된 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="39c8c-115">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="39c8c-116">-CurrentUser: 현재 사용자에 게 할당 된 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="39c8c-116">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="39c8c-117">기본값은 LocalMachine입니다.</span><span class="sxs-lookup"><span data-stu-id="39c8c-117">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="39c8c-118">열려는 X.509 인증서 저장소의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="39c8c-118">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="39c8c-119">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="39c8c-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="39c8c-120">-AddressBook: 다른 사용자에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="39c8c-120">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="39c8c-121">-AuthRoot: 타사 Ca (인증 기관) 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="39c8c-121">-   AuthRoot: Certificate store for third-party certificate authorities (CAs).</span></span><br /><span data-ttu-id="39c8c-122">-CertificateAuthority: 중개 Ca (인증 기관) 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="39c8c-122">-   CertificateAuthority: Certificate store for intermediate certificate authorities (CAs).</span></span><br /><span data-ttu-id="39c8c-123">-허용 안 함: 해지 된 인증서의 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="39c8c-123">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="39c8c-124">-My: 개인 인증서용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="39c8c-124">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="39c8c-125">-Root: 신뢰할 수 있는 루트 Ca (인증 기관) 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="39c8c-125">-   Root: Certificate store for trusted root certificate authorities (CAs).</span></span><br /><span data-ttu-id="39c8c-126">-개인 사용자: 직접 신뢰할 수 있는 사용자 및 리소스에 대 한 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="39c8c-126">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="39c8c-127">-신뢰할 수 있는 게시자: 직접 신뢰할 수 있는 게시자 용 인증서 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="39c8c-127">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="39c8c-128">기본값은 My입니다.</span><span class="sxs-lookup"><span data-stu-id="39c8c-128">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="39c8c-129">실행할 X.509 검색의 유형을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="39c8c-129">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="39c8c-130">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="39c8c-130">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="39c8c-131">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="39c8c-131">-   FindByThumbPrint</span></span><br /><span data-ttu-id="39c8c-132">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="39c8c-132">-   FindBySubjectName</span></span><br /><span data-ttu-id="39c8c-133">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="39c8c-133">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="39c8c-134">- FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="39c8c-134">-   FindByIssuerName</span></span><br /><span data-ttu-id="39c8c-135">- FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="39c8c-135">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="39c8c-136">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="39c8c-136">-   FindBySerialNumber</span></span><br /><span data-ttu-id="39c8c-137">- FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="39c8c-137">-   FindByTimeValid</span></span><br /><span data-ttu-id="39c8c-138">- FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="39c8c-138">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="39c8c-139">- FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="39c8c-139">-   FindByTemplateName</span></span><br /><span data-ttu-id="39c8c-140">- FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="39c8c-140">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="39c8c-141">- FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="39c8c-141">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="39c8c-142">- FindByExtension</span><span class="sxs-lookup"><span data-stu-id="39c8c-142">-   FindByExtension</span></span><br /><span data-ttu-id="39c8c-143">- FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="39c8c-143">-   FindByKeyUsage</span></span><br /><span data-ttu-id="39c8c-144">- FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="39c8c-144">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="39c8c-145">`findValue` 특성에 포함된 형식은 지정한 `X509FindType`의 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39c8c-145">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="39c8c-146">기본값은 FindBySubjectDistinguishedName입니다.</span><span class="sxs-lookup"><span data-stu-id="39c8c-146">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="39c8c-147">자식 요소</span><span class="sxs-lookup"><span data-stu-id="39c8c-147">Child Elements</span></span>  

 <span data-ttu-id="39c8c-148">없음</span><span class="sxs-lookup"><span data-stu-id="39c8c-148">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="39c8c-149">부모 요소</span><span class="sxs-lookup"><span data-stu-id="39c8c-149">Parent Elements</span></span>  
  
|<span data-ttu-id="39c8c-150">요소</span><span class="sxs-lookup"><span data-stu-id="39c8c-150">Element</span></span>|<span data-ttu-id="39c8c-151">설명</span><span class="sxs-lookup"><span data-stu-id="39c8c-151">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-servicecredentials.md)|<span data-ttu-id="39c8c-152">피어 노드에 대한 현재 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="39c8c-152">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39c8c-153">설명</span><span class="sxs-lookup"><span data-stu-id="39c8c-153">Remarks</span></span>  

 <span data-ttu-id="39c8c-154">이 구성 요소는 피어 메시에서 환경을 인증할 때 사용되는 `X509Certificate2` 인스턴스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="39c8c-154">This configuration element contains an `X509Certificate2` instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="39c8c-155">피어 투 피어 프로그래밍에 대 한 자세한 내용은 [피어 투 피어 네트워킹](../../../wcf/feature-details/peer-to-peer-networking.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="39c8c-155">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39c8c-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="39c8c-156">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>
- <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="39c8c-157">인증서 사용</span><span class="sxs-lookup"><span data-stu-id="39c8c-157">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="39c8c-158">피어 투 피어 네트워킹</span><span class="sxs-lookup"><span data-stu-id="39c8c-158">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="39c8c-159">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="39c8c-159">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="39c8c-160">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="39c8c-160">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="39c8c-161">피어 채널 애플리케이션 보안</span><span class="sxs-lookup"><span data-stu-id="39c8c-161">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="39c8c-162">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="39c8c-162">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
