---
description: 다음에 대해 자세히 알아보세요. <identity>
title: <identity>
ms.date: 03/30/2017
ms.assetid: c1d2ae56-e231-4a07-9c3f-9f13381dc0d8
ms.openlocfilehash: ceb4dc0e7efa6cd01204253001432ed1ef2c048e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802257"
---
# \<identity>

<span data-ttu-id="4e196-102">ID 요소를 사용하면 클라이언트 개발자가 서비스에 필요한 ID를 디자인 타임에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e196-102">The identity element allows a client developer to specify at design time the expected identity of the service.</span></span> <span data-ttu-id="4e196-103">클라이언트와 서비스 간의 핸드셰이크 프로세스에서 WCF (Windows Communication Foundation) 인프라는 예상 되는 서비스의 id가이 요소의 값과 일치 하는지 확인 하므로 인증 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e196-103">In the handshake process between the client and service, the Windows Communication Foundation (WCF) infrastructure will ensure that the identity of the expected service matches the values of this element, and thus can be authenticated.</span></span> <span data-ttu-id="4e196-104">자세한 내용은 [서비스 Id 및 인증](../../../wcf/feature-details/service-identity-and-authentication.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4e196-104">For more information, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<identity>**  
  
## <a name="syntax"></a><span data-ttu-id="4e196-105">구문</span><span class="sxs-lookup"><span data-stu-id="4e196-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4e196-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4e196-106">Attributes and Elements</span></span>  

 <span data-ttu-id="4e196-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4e196-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4e196-108">특성</span><span class="sxs-lookup"><span data-stu-id="4e196-108">Attributes</span></span>  

 <span data-ttu-id="4e196-109">없음</span><span class="sxs-lookup"><span data-stu-id="4e196-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4e196-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4e196-110">Child Elements</span></span>  
  
|<span data-ttu-id="4e196-111">요소</span><span class="sxs-lookup"><span data-stu-id="4e196-111">Element</span></span>|<span data-ttu-id="4e196-112">설명</span><span class="sxs-lookup"><span data-stu-id="4e196-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4e196-113">인증서(certificate)</span><span class="sxs-lookup"><span data-stu-id="4e196-113">certificate</span></span>|<span data-ttu-id="4e196-114">X.509 인증서의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e196-114">Specifies settings of an X.509 certificate.</span></span> <span data-ttu-id="4e196-115">이 요소는 <xref:System.ServiceModel.Configuration.CertificateElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4e196-115">This element is of type <xref:System.ServiceModel.Configuration.CertificateElement>.</span></span> <span data-ttu-id="4e196-116">이 요소에는 이 인증서로 인코딩된 값을 지정하는 문자열인 `encodedValue` 특성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e196-116">It contains an attribute `encodedValue` that is a string, which specifies the value encoded by this certificate.</span></span>|  
|<span data-ttu-id="4e196-117">certificateReference</span><span class="sxs-lookup"><span data-stu-id="4e196-117">certificateReference</span></span>|<span data-ttu-id="4e196-118">X.509 인증서 유효성 검사의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e196-118">Specifies settings for X.509 certificate validation.</span></span> <span data-ttu-id="4e196-119">이 요소는 <xref:System.ServiceModel.Configuration.CertificateReferenceElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4e196-119">This element is of type <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.</span></span>|  
|<span data-ttu-id="4e196-120">dns</span><span class="sxs-lookup"><span data-stu-id="4e196-120">dns</span></span>|<span data-ttu-id="4e196-121">서비스를 인증하는 데 사용되는 X.509 인증서의 DNS를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e196-121">Specifies the DNS of an X.509 certificate used to authenticate a service.</span></span> <span data-ttu-id="4e196-122">이 요소에는 문자열인 `value` 특성이 포함되며 실제 ID가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e196-122">This element contains an attribute `value` that is a string, and contains the actual identity.</span></span>|  
|<span data-ttu-id="4e196-123">rsa</span><span class="sxs-lookup"><span data-stu-id="4e196-123">rsa</span></span>|<span data-ttu-id="4e196-124">클라이언트에 서비스를 인증하는 데 사용되는 X.509 인증서의 RSA 필드 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e196-124">Specifies the value of the RSA field of an X.509 certificate used to authenticate a service to a client.</span></span> <span data-ttu-id="4e196-125">이 요소에는 문자열인 `value` 특성이 포함되며 실제 ID가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e196-125">This element contains an attribute `value` that is a string, and contains the actual identity</span></span>|  
|<span data-ttu-id="4e196-126">servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="4e196-126">servicePrincipalName</span></span>|<span data-ttu-id="4e196-127">서비스의 인스턴스를 고유하게 식별하기 위해 클라이언트에서 사용하는 사용자 이름인 SPN(서버 사용자 이름) ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e196-127">Specifies a server principal name (SPN) identity, which is the principal name used by a client to uniquely identify an instance of a service.</span></span> <span data-ttu-id="4e196-128">이 요소에는 문자열인 `value` 특성이 포함되며 실제 사용자 이름이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e196-128">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="4e196-129">이 요소는 <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4e196-129">This element is of type <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.</span></span>|  
|<span data-ttu-id="4e196-130">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="4e196-130">userPrincipalName</span></span>|<span data-ttu-id="4e196-131">네트워크 사용자의 로그온 이름 형식인 UPN(User Principal Name) ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e196-131">Specifies a user principal name (UPN) identity, which is the logon name type of a user on a network.</span></span> <span data-ttu-id="4e196-132">사용자 계정 이름은 Active Directory에 사용 되는 사용자 개체 이름, 기호 ( \@ ), 일반적으로 도메인 이름 시스템 부모 도메인으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e196-132">The user principal name consists of the user object name used in Active Directory, followed by the at symbol (\@) and then, typically, the Domain Name System parent domain.</span></span> <span data-ttu-id="4e196-133">예를 들어 Fabrikam.com 도메인 트리에 있는 Jeff에는 사용자 계정 이름이 있을 수 있습니다 [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com) .</span><span class="sxs-lookup"><span data-stu-id="4e196-133">For example, Jeff in the Fabrikam.com domain tree might have the user principal name [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com).</span></span>  <span data-ttu-id="4e196-134">이 요소에는 문자열인 `value` 특성이 포함되며 실제 사용자 이름이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e196-134">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="4e196-135">이 요소는 <xref:System.ServiceModel.Configuration.UserPrincipalNameElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4e196-135">This element is of type <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4e196-136">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4e196-136">Parent Elements</span></span>  
  
|<span data-ttu-id="4e196-137">요소</span><span class="sxs-lookup"><span data-stu-id="4e196-137">Element</span></span>|<span data-ttu-id="4e196-138">설명</span><span class="sxs-lookup"><span data-stu-id="4e196-138">Description</span></span>|  
|-------------|-----------------|  
|[\<custom>](custom.md)|<span data-ttu-id="4e196-139">netPeerTcpBinding에 대한 사용자 지정 피어 확인자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e196-139">Specifies a custom peer resolver for a netPeerTcpBinding.</span></span>|  
|[\<endpoint>](endpoint-element.md)|<span data-ttu-id="4e196-140">서비스 끝점을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e196-140">Configures service endpoints.</span></span>|  
|[<span data-ttu-id="4e196-141">\<client>의 \<endpoint></span><span class="sxs-lookup"><span data-stu-id="4e196-141">\<endpoint> of \<client></span></span>](endpoint-of-client.md)|<span data-ttu-id="4e196-142">채널 끝점을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e196-142">Configures channel endpoints.</span></span>|  
|[\<issuer>](issuer.md)|<span data-ttu-id="4e196-143">페더레이션 서비스에 대한 STS(보안 토큰 서비스)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e196-143">Specifies the Security Token Service (STS) for the federated service.</span></span>|  
|[\<issuerMetadata>](issuermetadata.md)|<span data-ttu-id="4e196-144">페더레이션 서비스의 STS(보안 토큰 서비스)에 대한 메타데이터 엔드포인트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e196-144">Specifies the metadata endpoint for the Security Token Service (STS) of a federated service.</span></span>|  
|[\<issuedTokenParameters>](issuedtokenparameters.md)|<span data-ttu-id="4e196-145">사용자 지정 바인딩에서 발급된 토큰에 대한 매개 변수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4e196-145">Defines parameters for an issued token in a custom binding.</span></span>|  
|[\<localIssuer>](localissuer.md)|<span data-ttu-id="4e196-146">로컬 STS(보안 토큰 서비스)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e196-146">Specifies a local Security Token Service (STS).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4e196-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4e196-147">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- [<span data-ttu-id="4e196-148">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="4e196-148">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="4e196-149">엔드포인트: 주소, 바인딩 및 계약</span><span class="sxs-lookup"><span data-stu-id="4e196-149">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
