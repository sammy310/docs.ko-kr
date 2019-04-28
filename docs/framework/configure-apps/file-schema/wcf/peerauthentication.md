---
title: <peerAuthentication>
ms.date: 03/30/2017
ms.assetid: ad545e6f-f06e-4549-ac92-09d758d5c636
ms.openlocfilehash: b627105dc4aae49557b0a6684569719622e13f08
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783333"
---
# <a name="peerauthentication"></a><span data-ttu-id="16930-101">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="16930-101">\<peerAuthentication></span></span>
<span data-ttu-id="16930-102">피어 노드에서 사용하는 피어 인증서에 대한 인증 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="16930-102">Specifies authentication settings for a peer certificate used by a peer node.</span></span>  
  
 <span data-ttu-id="16930-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="16930-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="16930-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="16930-104">\<behaviors></span></span>  
<span data-ttu-id="16930-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="16930-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="16930-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="16930-106">\<behavior></span></span>  
<span data-ttu-id="16930-107">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="16930-107">\<serviceCredentials></span></span>  
<span data-ttu-id="16930-108">\<peer></span><span class="sxs-lookup"><span data-stu-id="16930-108">\<peer></span></span>  
<span data-ttu-id="16930-109">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="16930-109">\<peerAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16930-110">구문</span><span class="sxs-lookup"><span data-stu-id="16930-110">Syntax</span></span>  
  
```xml  
<peerAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                    certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                    revocationMode="NoCheck/Online/Offline"
                    trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="16930-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="16930-111">Attributes and Elements</span></span>  
 <span data-ttu-id="16930-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="16930-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="16930-113">특성</span><span class="sxs-lookup"><span data-stu-id="16930-113">Attributes</span></span>  
  
|<span data-ttu-id="16930-114">특성</span><span class="sxs-lookup"><span data-stu-id="16930-114">Attribute</span></span>|<span data-ttu-id="16930-115">설명</span><span class="sxs-lookup"><span data-stu-id="16930-115">Description</span></span>|  
|---------------|-----------------|  
|`certificateValidationMode`|<span data-ttu-id="16930-116">선택적 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="16930-116">Optional enumeration.</span></span> <span data-ttu-id="16930-117">자격 증명의 유효성을 검사하는 데 사용되는 세 가지 모드 중 하나를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="16930-117">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="16930-118">이 특성은 <xref:System.ServiceModel.Security.X509CertificateValidationMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="16930-118">This attribute is of type <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="16930-119">`Custom`으로 설정되면 `customCertificateValidator`도 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16930-119">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="16930-120">선택적 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="16930-120">Optional string.</span></span> <span data-ttu-id="16930-121">사용자 지정 형식의 유효성을 검사하는 데 사용되는 형식 및 어셈블리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="16930-121">Specifies a type and assembly used to validate a custom type.</span></span> <span data-ttu-id="16930-122">이 특성은 `certificateValidationMode`가 `Custom`으로 설정되어 있을 때 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16930-122">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span> <span data-ttu-id="16930-123">이 특성은 <xref:System.IdentityModel.Selectors.X509CertificateValidator> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="16930-123">This attribute is of type <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="16930-124">Windows Communication Foundation (WCF) 기본 피어 신뢰할 수 있는 사용자 저장소를 대상으로 피어 인증서를 확인 하는 인증서 유효성 검사기를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="16930-124">Windows Communication Foundation (WCF) provides a default peer certificate validator that verifies the peer certificate against the trusted people store.</span></span> <span data-ttu-id="16930-125">이 검사기는 또한 인증서가 유효한 루트에 연결되었는지도 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="16930-125">It also verifies that the certificate chains up to a valid root.</span></span> <span data-ttu-id="16930-126">사용자 지정 유효성 검사기를 사용하여 다른 동작을 지정하고, 이 특성을 사용하여 사용자 지정 유효성 검사기의 위치를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16930-126">You can implement a custom validator to specify a different behavior and use this attribute to point to the custom validator.</span></span>|  
|`revocationMode`|<span data-ttu-id="16930-127">선택적 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="16930-127">Optional enumeration.</span></span> <span data-ttu-id="16930-128">인증서 해지 모드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="16930-128">Specifies the certificate revocation mode.</span></span> <span data-ttu-id="16930-129">이 특성은 <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="16930-129">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span> <span data-ttu-id="16930-130">시스템에서는 해지된 인증서 목록에서 피어 인증서를 검색하여 해당 피어 인증서가 해지되지 않았는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="16930-130">The system verifies that the peer certificate has not been revoked by looking it up in the revoked certificate list.</span></span> <span data-ttu-id="16930-131">이러한 확인은 온라인으로 확인하거나 캐시된 해지 목록을 확인하여 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="16930-131">This check can be performed either by checking online or against a cached revocation list.</span></span> <span data-ttu-id="16930-132">이 특성을 NoCheck로 설정하면 해지 확인을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16930-132">Revocation checking can be turned off by setting this attribute to NoCheck.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="16930-133">선택적 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="16930-133">Optional enumeration.</span></span> <span data-ttu-id="16930-134">WCF 보안 시스템에서 피어 인증서가 확인 하는 위치를 신뢰할 수 있는 저장소 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="16930-134">Specifies the trusted store location where the peer certificate is validated by the WCF security system.</span></span> <span data-ttu-id="16930-135">이 특성은 <xref:System.Security.Cryptography.X509Certificates.StoreLocation> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="16930-135">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="16930-136">자식 요소</span><span class="sxs-lookup"><span data-stu-id="16930-136">Child Elements</span></span>  
 <span data-ttu-id="16930-137">없음</span><span class="sxs-lookup"><span data-stu-id="16930-137">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="16930-138">부모 요소</span><span class="sxs-lookup"><span data-stu-id="16930-138">Parent Elements</span></span>  
  
|<span data-ttu-id="16930-139">요소</span><span class="sxs-lookup"><span data-stu-id="16930-139">Element</span></span>|<span data-ttu-id="16930-140">설명</span><span class="sxs-lookup"><span data-stu-id="16930-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="16930-141">\<peer></span><span class="sxs-lookup"><span data-stu-id="16930-141">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="16930-142">피어 노드에 대한 현재 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="16930-142">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16930-143">설명</span><span class="sxs-lookup"><span data-stu-id="16930-143">Remarks</span></span>  
 <span data-ttu-id="16930-144">`<authentication>` 요소는 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> 클래스에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="16930-144">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="16930-145">이 요소는 메시의 환경 간 인증 중에 호출되는 유효성 검사기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="16930-145">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="16930-146">새 피어는 환경 연결을 설정하려고 할 때 응답 피어에 해당 자격 증명을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="16930-146">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="16930-147">원격 상대방의 자격 증명의 유효성 검사를 위해 응답자의 유효성 검사기가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="16930-147">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="16930-148">메시에서 피어 연결이 설정될 때마다 두 피어는 상호 인증됩니다. 즉, 양쪽에서 유효성 검사기가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="16930-148">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16930-149">참고자료</span><span class="sxs-lookup"><span data-stu-id="16930-149">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="16930-150">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="16930-150">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="16930-151">피어 투 피어 네트워킹</span><span class="sxs-lookup"><span data-stu-id="16930-151">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="16930-152">[피어 채널 메시지 인증](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="16930-152">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="16930-153">[피어 채널 사용자 지정 인증](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="16930-153">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="16930-154">피어 채널 애플리케이션 보안</span><span class="sxs-lookup"><span data-stu-id="16930-154">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
