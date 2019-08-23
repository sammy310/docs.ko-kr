---
title: <messageSenderAuthentication> 요소
ms.date: 03/30/2017
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
ms.openlocfilehash: 1e63b6fa93e1abfa87c83da4b5d46f492c59b9bc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931367"
---
# <a name="messagesenderauthentication-element"></a><span data-ttu-id="af953-102">\<h > 요소</span><span class="sxs-lookup"><span data-stu-id="af953-102">\<messageSenderAuthentication> element</span></span>
<span data-ttu-id="af953-103">피어 투 피어 메시지 발신자에 대한 인증 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="af953-103">Specifies authentication options for peer-to-peer message senders.</span></span>  
  
 <span data-ttu-id="af953-104">피어 투 피어 프로그래밍에 대 한 자세한 내용은 [피어 투 피어 네트워킹](../../../wcf/feature-details/peer-to-peer-networking.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="af953-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
 <span data-ttu-id="af953-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="af953-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="af953-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="af953-106">\<behaviors></span></span>  
<span data-ttu-id="af953-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="af953-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="af953-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="af953-108">\<behavior></span></span>  
<span data-ttu-id="af953-109">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="af953-109">\<clientCredentials></span></span>  
<span data-ttu-id="af953-110">\<peer></span><span class="sxs-lookup"><span data-stu-id="af953-110">\<peer></span></span>  
<span data-ttu-id="af953-111">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="af953-111">\<messageSenderAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af953-112">구문</span><span class="sxs-lookup"><span data-stu-id="af953-112">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af953-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="af953-113">Attributes and Elements</span></span>  
 <span data-ttu-id="af953-114">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="af953-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af953-115">특성</span><span class="sxs-lookup"><span data-stu-id="af953-115">Attributes</span></span>  
  
|<span data-ttu-id="af953-116">특성</span><span class="sxs-lookup"><span data-stu-id="af953-116">Attribute</span></span>|<span data-ttu-id="af953-117">Description</span><span class="sxs-lookup"><span data-stu-id="af953-117">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="af953-118">사용자 지정 형식의 유효성을 검사하는 데 사용되는 형식 및 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="af953-118">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="af953-119">이 특성은 `certificateValidationMode`가 `Custom`으로 설정되어 있을 때 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af953-119">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="af953-120">자격 증명의 유효성을 검사하는 데 사용되는 세 가지 모드 중 하나를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="af953-120">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="af953-121">`Custom`으로 설정되면 `customCertificateValidator`도 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af953-121">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`revocationMode`|<span data-ttu-id="af953-122">CRL(해지된 인증서 목록)을 검사하는 데 사용되는 모드 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="af953-122">One of the modes used to check for a revoked certificate lists (CRL).</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="af953-123">시스템 저장소 위치 `LocalMachine` 또는 `CurrentUser` 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="af953-123">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="af953-124">서비스 인증서가 클라이언트와 협상될 때 이 값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="af953-124">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="af953-125">지정 된 저장소 위치에 있는 **신뢰할 수 있는 사용자** 저장소에 대해 유효성 검사가 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af953-125">Validation is performed against the **Trusted People** store in the specified store location.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="af953-126">customCertificateValidatorType 특성</span><span class="sxs-lookup"><span data-stu-id="af953-126">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="af953-127">값</span><span class="sxs-lookup"><span data-stu-id="af953-127">Value</span></span>|<span data-ttu-id="af953-128">설명</span><span class="sxs-lookup"><span data-stu-id="af953-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="af953-129">String</span><span class="sxs-lookup"><span data-stu-id="af953-129">String</span></span>|<span data-ttu-id="af953-130">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="af953-130">Optional.</span></span> <span data-ttu-id="af953-131">형식 이름 및 어셈블리와 형식을 찾는 데 사용되는 기타 데이터를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="af953-131">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="af953-132">적어도 네임스페이스 및 형식 이름이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="af953-132">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="af953-133">선택적 정보로는 어셈블리 이름, 버전 번호, 문화권 및 공개 키 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af953-133">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="af953-134">certificateValidationMode 특성</span><span class="sxs-lookup"><span data-stu-id="af953-134">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="af953-135">값</span><span class="sxs-lookup"><span data-stu-id="af953-135">Value</span></span>|<span data-ttu-id="af953-136">Description</span><span class="sxs-lookup"><span data-stu-id="af953-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="af953-137">열거형</span><span class="sxs-lookup"><span data-stu-id="af953-137">Enumeration</span></span>|<span data-ttu-id="af953-138">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="af953-138">Optional.</span></span> <span data-ttu-id="af953-139">`None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom` 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="af953-139">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="af953-140">기본값은 `ChainTrust`입니다.</span><span class="sxs-lookup"><span data-stu-id="af953-140">The default is `ChainTrust`.</span></span> <span data-ttu-id="af953-141">기본값은 `ChainTrust`입니다.</span><span class="sxs-lookup"><span data-stu-id="af953-141">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="af953-142">자세한 내용은 [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="af953-142">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="af953-143">revocationMode 특성</span><span class="sxs-lookup"><span data-stu-id="af953-143">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="af953-144">값</span><span class="sxs-lookup"><span data-stu-id="af953-144">Value</span></span>|<span data-ttu-id="af953-145">설명</span><span class="sxs-lookup"><span data-stu-id="af953-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="af953-146">열거형</span><span class="sxs-lookup"><span data-stu-id="af953-146">Enumeration</span></span>|<span data-ttu-id="af953-147">`NoCheck`, `Online`, `Offline` 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="af953-147">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="af953-148">기본값은 `Online`입니다.</span><span class="sxs-lookup"><span data-stu-id="af953-148">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="af953-149">자세한 내용은 [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="af953-149">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="af953-150">trustedStoreLocation 특성</span><span class="sxs-lookup"><span data-stu-id="af953-150">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="af953-151">값</span><span class="sxs-lookup"><span data-stu-id="af953-151">Value</span></span>|<span data-ttu-id="af953-152">Description</span><span class="sxs-lookup"><span data-stu-id="af953-152">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="af953-153">열거형</span><span class="sxs-lookup"><span data-stu-id="af953-153">Enumeration</span></span>|<span data-ttu-id="af953-154">`LocalMachine` 또는 `CurrentUser` 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="af953-154">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="af953-155">기본값은 `CurrentUser`입니다.</span><span class="sxs-lookup"><span data-stu-id="af953-155">The default is `CurrentUser`.</span></span> <span data-ttu-id="af953-156">시스템 계정으로 클라이언트 애플리케이션을 실행하는 경우 인증서는 대개 `LocalMachine`에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af953-156">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="af953-157">사용자 계정으로 클라이언트 애플리케이션을 실행하는 경우 인증서는 대개 `CurrentUser`에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af953-157">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span> <span data-ttu-id="af953-158">기본값은 `CurrentUser`입니다.</span><span class="sxs-lookup"><span data-stu-id="af953-158">The default is `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="af953-159">자식 요소</span><span class="sxs-lookup"><span data-stu-id="af953-159">Child Elements</span></span>  
 <span data-ttu-id="af953-160">없음</span><span class="sxs-lookup"><span data-stu-id="af953-160">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="af953-161">부모 요소</span><span class="sxs-lookup"><span data-stu-id="af953-161">Parent Elements</span></span>  
  
|<span data-ttu-id="af953-162">요소</span><span class="sxs-lookup"><span data-stu-id="af953-162">Element</span></span>|<span data-ttu-id="af953-163">Description</span><span class="sxs-lookup"><span data-stu-id="af953-163">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="af953-164">\<peer></span><span class="sxs-lookup"><span data-stu-id="af953-164">\<peer></span></span>](peer-of-clientcredentials-element.md)|<span data-ttu-id="af953-165">피어 서비스에 대해 클라이언트를 인증하는 데 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="af953-165">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af953-166">설명</span><span class="sxs-lookup"><span data-stu-id="af953-166">Remarks</span></span>  
 <span data-ttu-id="af953-167">메시지 인증을 선택하면 이 요소를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af953-167">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="af953-168">출력 채널의 경우 각 메시지는 [ \<인증서 >](certificate-element.md)에서 제공 하는 인증서를 사용 하 여 서명 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af953-168">For output channels, each message is signed using the certificate provided by [\<certificate>](certificate-element.md).</span></span> <span data-ttu-id="af953-169">모든 메시지는 애플리케이션에 배달되기 전에 이 요소의 `customCertificateValidatorType` 특성에 지정된 유효성 검사기를 사용하여 메시지 자격 증명과 비교하여 검사됩니다.</span><span class="sxs-lookup"><span data-stu-id="af953-169">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="af953-170">유효성 검사기는 자격 증명을 수락하거나 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af953-170">The validator can either accept or reject the credential.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af953-171">예제</span><span class="sxs-lookup"><span data-stu-id="af953-171">Example</span></span>  
 <span data-ttu-id="af953-172">다음 코드에서는 메시지 발신자 유효성 검사 모드를 `PeerOrChainTrust`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="af953-172">The following code sets the message sender validation mode to `PeerOrChainTrust`.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <peer>
          <certificate findValue="www.contoso.com"
                       storeLocation="LocalMachine"
                       x509FindType="FindByIssuerName" />
          <messageSenderAuthentication certificateValidationMode="PeerOrChainTrust" />
          <messageSenderAuthentication certificateValidationMode="None" />
        </peer>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="af953-173">참고자료</span><span class="sxs-lookup"><span data-stu-id="af953-173">See also</span></span>

- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="af953-174">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="af953-174">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="af953-175">피어 투 피어 네트워킹</span><span class="sxs-lookup"><span data-stu-id="af953-175">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="af953-176">[피어 채널 메시지 인증](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="af953-176">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="af953-177">[피어 채널 사용자 지정 인증](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="af953-177">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="af953-178">피어 채널 애플리케이션 보안</span><span class="sxs-lookup"><span data-stu-id="af953-178">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
