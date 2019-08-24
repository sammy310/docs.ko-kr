---
title: <identity>
ms.date: 03/30/2017
ms.assetid: c1d2ae56-e231-4a07-9c3f-9f13381dc0d8
ms.openlocfilehash: 262ac9be6d5ce6466cf9aff33c0c2791c0e149dd
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/23/2019
ms.locfileid: "69988376"
---
# <a name="identity"></a><span data-ttu-id="91d9e-101">\<identity></span><span class="sxs-lookup"><span data-stu-id="91d9e-101">\<identity></span></span>
<span data-ttu-id="91d9e-102">ID 요소를 사용하면 클라이언트 개발자가 서비스에 필요한 ID를 디자인 타임에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91d9e-102">The identity element allows a client developer to specify at design time the expected identity of the service.</span></span> <span data-ttu-id="91d9e-103">클라이언트와 서비스 간의 핸드셰이크 프로세스에서 WCF (Windows Communication Foundation) 인프라는 예상 되는 서비스의 id가이 요소의 값과 일치 하는지 확인 하므로 인증 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91d9e-103">In the handshake process between the client and service, the Windows Communication Foundation (WCF) infrastructure will ensure that the identity of the expected service matches the values of this element, and thus can be authenticated.</span></span> <span data-ttu-id="91d9e-104">자세한 내용은 [서비스 Id 및 인증](../../../wcf/feature-details/service-identity-and-authentication.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="91d9e-104">For more information, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="91d9e-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="91d9e-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="91d9e-106">\<client></span><span class="sxs-lookup"><span data-stu-id="91d9e-106">\<client></span></span>  
<span data-ttu-id="91d9e-107">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="91d9e-107">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91d9e-108">구문</span><span class="sxs-lookup"><span data-stu-id="91d9e-108">Syntax</span></span>  
  
```xml  
<identity>
  <certificate encodedValue="String" />
  <certificateReference findValue="String"
                        isChainIncluded="Boolean"
                        storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                        storeLocation="LocalMachine/CurrentUser"
                        X509FindType="Enumeration" />
  <dns value="String" />
  <rsa value="String" />
  <servicePrincipalName value="String" />
  <userPrincipalName value="String" />
</identity>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91d9e-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="91d9e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="91d9e-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="91d9e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91d9e-111">특성</span><span class="sxs-lookup"><span data-stu-id="91d9e-111">Attributes</span></span>  
 <span data-ttu-id="91d9e-112">없음</span><span class="sxs-lookup"><span data-stu-id="91d9e-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="91d9e-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="91d9e-113">Child Elements</span></span>  
  
|<span data-ttu-id="91d9e-114">요소</span><span class="sxs-lookup"><span data-stu-id="91d9e-114">Element</span></span>|<span data-ttu-id="91d9e-115">설명</span><span class="sxs-lookup"><span data-stu-id="91d9e-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="91d9e-116">인증서(certificate)</span><span class="sxs-lookup"><span data-stu-id="91d9e-116">certificate</span></span>|<span data-ttu-id="91d9e-117">X.509 인증서의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="91d9e-117">Specifies settings of an X.509 certificate.</span></span> <span data-ttu-id="91d9e-118">이 요소는 <xref:System.ServiceModel.Configuration.CertificateElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="91d9e-118">This element is of type <xref:System.ServiceModel.Configuration.CertificateElement>.</span></span> <span data-ttu-id="91d9e-119">이 요소에는 이 인증서로 인코딩된 값을 지정하는 문자열인 `encodedValue` 특성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91d9e-119">It contains an attribute `encodedValue` that is a string, which specifies the value encoded by this certificate.</span></span>|  
|<span data-ttu-id="91d9e-120">certificateReference</span><span class="sxs-lookup"><span data-stu-id="91d9e-120">certificateReference</span></span>|<span data-ttu-id="91d9e-121">X.509 인증서 유효성 검사의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="91d9e-121">Specifies settings for X.509 certificate validation.</span></span> <span data-ttu-id="91d9e-122">이 요소는 <xref:System.ServiceModel.Configuration.CertificateReferenceElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="91d9e-122">This element is of type <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.</span></span>|  
|<span data-ttu-id="91d9e-123">dns</span><span class="sxs-lookup"><span data-stu-id="91d9e-123">dns</span></span>|<span data-ttu-id="91d9e-124">서비스를 인증하는 데 사용되는 X.509 인증서의 DNS를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="91d9e-124">Specifies the DNS of an X.509 certificate used to authenticate a service.</span></span> <span data-ttu-id="91d9e-125">이 요소에는 문자열인 `value` 특성이 포함되며 실제 ID가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="91d9e-125">This element contains an attribute `value` that is a string, and contains the actual identity.</span></span>|  
|<span data-ttu-id="91d9e-126">rsa</span><span class="sxs-lookup"><span data-stu-id="91d9e-126">rsa</span></span>|<span data-ttu-id="91d9e-127">클라이언트에 서비스를 인증하는 데 사용되는 X.509 인증서의 RSA 필드 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="91d9e-127">Specifies the value of the RSA field of an X.509 certificate used to authenticate a service to a client.</span></span> <span data-ttu-id="91d9e-128">이 요소에는 문자열인 `value` 특성이 포함되며 실제 ID가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="91d9e-128">This element contains an attribute `value` that is a string, and contains the actual identity</span></span>|  
|<span data-ttu-id="91d9e-129">servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="91d9e-129">servicePrincipalName</span></span>|<span data-ttu-id="91d9e-130">서비스의 인스턴스를 고유하게 식별하기 위해 클라이언트에서 사용하는 사용자 이름인 SPN(서버 사용자 이름) ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="91d9e-130">Specifies a server principal name (SPN) identity, which is the principal name used by a client to uniquely identify an instance of a service.</span></span> <span data-ttu-id="91d9e-131">이 요소에는 문자열인 `value` 특성이 포함되며 실제 사용자 이름이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="91d9e-131">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="91d9e-132">이 요소는 <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="91d9e-132">This element is of type <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.</span></span>|  
|<span data-ttu-id="91d9e-133">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="91d9e-133">userPrincipalName</span></span>|<span data-ttu-id="91d9e-134">네트워크 사용자의 로그온 이름 형식인 UPN(User Principal Name) ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="91d9e-134">Specifies a user principal name (UPN) identity, which is the logon name type of a user on a network.</span></span> <span data-ttu-id="91d9e-135">사용자 계정 이름은 Active Directory에 사용 되는 사용자 개체 이름, 기호 (\@), 일반적으로 도메인 이름 시스템 부모 도메인으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91d9e-135">The user principal name consists of the user object name used in Active Directory, followed by the at symbol (\@) and then, typically, the Domain Name System parent domain.</span></span> <span data-ttu-id="91d9e-136">예를 들어, Fabrikam.com 도메인 트리에 있는 Jeff 사용자 계정 이름 있을 [ jeff@fabrikam.com ](mailto:jeffsmith@fabrikam.com)합니다.</span><span class="sxs-lookup"><span data-stu-id="91d9e-136">For example, Jeff in the Fabrikam.com domain tree might have the user principal name [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com).</span></span>  <span data-ttu-id="91d9e-137">이 요소에는 문자열인 `value` 특성이 포함되며 실제 사용자 이름이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="91d9e-137">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="91d9e-138">이 요소는 <xref:System.ServiceModel.Configuration.UserPrincipalNameElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="91d9e-138">This element is of type <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="91d9e-139">부모 요소</span><span class="sxs-lookup"><span data-stu-id="91d9e-139">Parent Elements</span></span>  
  
|<span data-ttu-id="91d9e-140">요소</span><span class="sxs-lookup"><span data-stu-id="91d9e-140">Element</span></span>|<span data-ttu-id="91d9e-141">Description</span><span class="sxs-lookup"><span data-stu-id="91d9e-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="91d9e-142">\<custom></span><span class="sxs-lookup"><span data-stu-id="91d9e-142">\<custom></span></span>](custom.md)|<span data-ttu-id="91d9e-143">netPeerTcpBinding에 대한 사용자 지정 피어 확인자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="91d9e-143">Specifies a custom peer resolver for a netPeerTcpBinding.</span></span>|  
|[<span data-ttu-id="91d9e-144">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="91d9e-144">\<endpoint></span></span>](endpoint-element.md)|<span data-ttu-id="91d9e-145">서비스 끝점을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="91d9e-145">Configures service endpoints.</span></span>|  
|[<span data-ttu-id="91d9e-146">\<클라이언트 >의 \<끝점 ></span><span class="sxs-lookup"><span data-stu-id="91d9e-146">\<endpoint> of \<client></span></span>](endpoint-of-client.md)|<span data-ttu-id="91d9e-147">채널 끝점을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="91d9e-147">Configures channel endpoints.</span></span>|  
|[<span data-ttu-id="91d9e-148">\<issuer></span><span class="sxs-lookup"><span data-stu-id="91d9e-148">\<issuer></span></span>](issuer.md)|<span data-ttu-id="91d9e-149">페더레이션 서비스에 대한 STS(보안 토큰 서비스)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="91d9e-149">Specifies the Security Token Service (STS) for the federated service.</span></span>|  
|[<span data-ttu-id="91d9e-150">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="91d9e-150">\<issuerMetadata></span></span>](issuermetadata.md)|<span data-ttu-id="91d9e-151">페더레이션 서비스의 STS(보안 토큰 서비스)에 대한 메타데이터 엔드포인트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="91d9e-151">Specifies the metadata endpoint for the Security Token Service (STS) of a federated service.</span></span>|  
|[<span data-ttu-id="91d9e-152">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="91d9e-152">\<issuedTokenParameters></span></span>](issuedtokenparameters.md)|<span data-ttu-id="91d9e-153">사용자 지정 바인딩에서 발급된 토큰에 대한 매개 변수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="91d9e-153">Defines parameters for an issued token in a custom binding.</span></span>|  
|[<span data-ttu-id="91d9e-154">\<localIssuer></span><span class="sxs-lookup"><span data-stu-id="91d9e-154">\<localIssuer></span></span>](localissuer.md)|<span data-ttu-id="91d9e-155">로컬 STS(보안 토큰 서비스)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="91d9e-155">Specifies a local Security Token Service (STS).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="91d9e-156">참고자료</span><span class="sxs-lookup"><span data-stu-id="91d9e-156">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- [<span data-ttu-id="91d9e-157">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="91d9e-157">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="91d9e-158">종점 주소, 바인딩 및 계약</span><span class="sxs-lookup"><span data-stu-id="91d9e-158">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
