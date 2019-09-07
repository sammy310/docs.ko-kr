---
title: <messageSenderAuthentication> 요소
ms.date: 03/30/2017
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
ms.openlocfilehash: bab0e50d7feba3ea55d505be07cfa41427a5cbbc
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397784"
---
# <a name="messagesenderauthentication-element"></a><span data-ttu-id="4633b-102">\<h > 요소</span><span class="sxs-lookup"><span data-stu-id="4633b-102">\<messageSenderAuthentication> element</span></span>
<span data-ttu-id="4633b-103">피어 투 피어 메시지 발신자에 대한 인증 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4633b-103">Specifies authentication options for peer-to-peer message senders.</span></span>  
  
 <span data-ttu-id="4633b-104">피어 투 피어 프로그래밍에 대 한 자세한 내용은 [피어 투 피어 네트워킹](../../../wcf/feature-details/peer-to-peer-networking.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4633b-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
<span data-ttu-id="4633b-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4633b-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4633b-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4633b-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4633b-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="4633b-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="4633b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="4633b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="4633b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="4633b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="4633b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="4633b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="4633b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<피어 >** ](peer-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="4633b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)</span></span>\
<span data-ttu-id="4633b-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<h >**</span><span class="sxs-lookup"><span data-stu-id="4633b-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<messageSenderAuthentication>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4633b-113">구문</span><span class="sxs-lookup"><span data-stu-id="4633b-113">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4633b-114">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4633b-114">Attributes and Elements</span></span>  
 <span data-ttu-id="4633b-115">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4633b-115">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4633b-116">특성</span><span class="sxs-lookup"><span data-stu-id="4633b-116">Attributes</span></span>  
  
|<span data-ttu-id="4633b-117">특성</span><span class="sxs-lookup"><span data-stu-id="4633b-117">Attribute</span></span>|<span data-ttu-id="4633b-118">설명</span><span class="sxs-lookup"><span data-stu-id="4633b-118">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="4633b-119">사용자 지정 형식의 유효성을 검사하는 데 사용되는 형식 및 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="4633b-119">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="4633b-120">이 특성은 `certificateValidationMode`가 `Custom`으로 설정되어 있을 때 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4633b-120">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="4633b-121">자격 증명의 유효성을 검사하는 데 사용되는 세 가지 모드 중 하나를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4633b-121">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="4633b-122">`Custom`으로 설정되면 `customCertificateValidator`도 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4633b-122">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`revocationMode`|<span data-ttu-id="4633b-123">CRL(해지된 인증서 목록)을 검사하는 데 사용되는 모드 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="4633b-123">One of the modes used to check for a revoked certificate lists (CRL).</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="4633b-124">시스템 저장소 위치 `LocalMachine` 또는 `CurrentUser` 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="4633b-124">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="4633b-125">서비스 인증서가 클라이언트와 협상될 때 이 값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4633b-125">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="4633b-126">지정 된 저장소 위치에 있는 **신뢰할 수 있는 사용자** 저장소에 대해 유효성 검사가 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4633b-126">Validation is performed against the **Trusted People** store in the specified store location.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="4633b-127">customCertificateValidatorType 특성</span><span class="sxs-lookup"><span data-stu-id="4633b-127">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="4633b-128">값</span><span class="sxs-lookup"><span data-stu-id="4633b-128">Value</span></span>|<span data-ttu-id="4633b-129">Description</span><span class="sxs-lookup"><span data-stu-id="4633b-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4633b-130">문자열</span><span class="sxs-lookup"><span data-stu-id="4633b-130">String</span></span>|<span data-ttu-id="4633b-131">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4633b-131">Optional.</span></span> <span data-ttu-id="4633b-132">형식 이름 및 어셈블리와 형식을 찾는 데 사용되는 기타 데이터를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4633b-132">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="4633b-133">적어도 네임스페이스 및 형식 이름이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4633b-133">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="4633b-134">선택적 정보로는 어셈블리 이름, 버전 번호, 문화권 및 공개 키 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4633b-134">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="4633b-135">certificateValidationMode 특성</span><span class="sxs-lookup"><span data-stu-id="4633b-135">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="4633b-136">값</span><span class="sxs-lookup"><span data-stu-id="4633b-136">Value</span></span>|<span data-ttu-id="4633b-137">Description</span><span class="sxs-lookup"><span data-stu-id="4633b-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4633b-138">열거형</span><span class="sxs-lookup"><span data-stu-id="4633b-138">Enumeration</span></span>|<span data-ttu-id="4633b-139">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4633b-139">Optional.</span></span> <span data-ttu-id="4633b-140">`None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom` 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="4633b-140">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="4633b-141">기본값은 `ChainTrust`입니다.</span><span class="sxs-lookup"><span data-stu-id="4633b-141">The default is `ChainTrust`.</span></span> <span data-ttu-id="4633b-142">기본값은 `ChainTrust`입니다.</span><span class="sxs-lookup"><span data-stu-id="4633b-142">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="4633b-143">자세한 내용은 [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4633b-143">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="4633b-144">revocationMode 특성</span><span class="sxs-lookup"><span data-stu-id="4633b-144">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="4633b-145">값</span><span class="sxs-lookup"><span data-stu-id="4633b-145">Value</span></span>|<span data-ttu-id="4633b-146">Description</span><span class="sxs-lookup"><span data-stu-id="4633b-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4633b-147">열거형</span><span class="sxs-lookup"><span data-stu-id="4633b-147">Enumeration</span></span>|<span data-ttu-id="4633b-148">`NoCheck`, `Online`, `Offline` 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="4633b-148">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="4633b-149">기본값은 `Online`입니다.</span><span class="sxs-lookup"><span data-stu-id="4633b-149">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="4633b-150">자세한 내용은 [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4633b-150">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="4633b-151">trustedStoreLocation 특성</span><span class="sxs-lookup"><span data-stu-id="4633b-151">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="4633b-152">값</span><span class="sxs-lookup"><span data-stu-id="4633b-152">Value</span></span>|<span data-ttu-id="4633b-153">Description</span><span class="sxs-lookup"><span data-stu-id="4633b-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4633b-154">열거형</span><span class="sxs-lookup"><span data-stu-id="4633b-154">Enumeration</span></span>|<span data-ttu-id="4633b-155">`LocalMachine` 또는 `CurrentUser` 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="4633b-155">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="4633b-156">기본값은 `CurrentUser`입니다.</span><span class="sxs-lookup"><span data-stu-id="4633b-156">The default is `CurrentUser`.</span></span> <span data-ttu-id="4633b-157">시스템 계정으로 클라이언트 애플리케이션을 실행하는 경우 인증서는 대개 `LocalMachine`에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4633b-157">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="4633b-158">사용자 계정으로 클라이언트 애플리케이션을 실행하는 경우 인증서는 대개 `CurrentUser`에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4633b-158">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span> <span data-ttu-id="4633b-159">기본값은 `CurrentUser`입니다.</span><span class="sxs-lookup"><span data-stu-id="4633b-159">The default is `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4633b-160">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4633b-160">Child Elements</span></span>  
 <span data-ttu-id="4633b-161">없음</span><span class="sxs-lookup"><span data-stu-id="4633b-161">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4633b-162">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4633b-162">Parent Elements</span></span>  
  
|<span data-ttu-id="4633b-163">요소</span><span class="sxs-lookup"><span data-stu-id="4633b-163">Element</span></span>|<span data-ttu-id="4633b-164">설명</span><span class="sxs-lookup"><span data-stu-id="4633b-164">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4633b-165">\<peer></span><span class="sxs-lookup"><span data-stu-id="4633b-165">\<peer></span></span>](peer-of-clientcredentials-element.md)|<span data-ttu-id="4633b-166">피어 서비스에 대해 클라이언트를 인증하는 데 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4633b-166">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4633b-167">설명</span><span class="sxs-lookup"><span data-stu-id="4633b-167">Remarks</span></span>  
 <span data-ttu-id="4633b-168">메시지 인증을 선택하면 이 요소를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4633b-168">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="4633b-169">출력 채널의 경우 각 메시지는 [ \<인증서 >](certificate-element.md)에서 제공 하는 인증서를 사용 하 여 서명 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4633b-169">For output channels, each message is signed using the certificate provided by [\<certificate>](certificate-element.md).</span></span> <span data-ttu-id="4633b-170">모든 메시지는 애플리케이션에 배달되기 전에 이 요소의 `customCertificateValidatorType` 특성에 지정된 유효성 검사기를 사용하여 메시지 자격 증명과 비교하여 검사됩니다.</span><span class="sxs-lookup"><span data-stu-id="4633b-170">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="4633b-171">유효성 검사기는 자격 증명을 수락하거나 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4633b-171">The validator can either accept or reject the credential.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4633b-172">예제</span><span class="sxs-lookup"><span data-stu-id="4633b-172">Example</span></span>  
 <span data-ttu-id="4633b-173">다음 코드에서는 메시지 발신자 유효성 검사 모드를 `PeerOrChainTrust`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4633b-173">The following code sets the message sender validation mode to `PeerOrChainTrust`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4633b-174">참고자료</span><span class="sxs-lookup"><span data-stu-id="4633b-174">See also</span></span>

- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="4633b-175">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="4633b-175">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="4633b-176">피어 투 피어 네트워킹</span><span class="sxs-lookup"><span data-stu-id="4633b-176">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="4633b-177">[피어 채널 메시지 인증](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="4633b-177">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="4633b-178">[피어 채널 사용자 지정 인증](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="4633b-178">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="4633b-179">피어 채널 애플리케이션 보안</span><span class="sxs-lookup"><span data-stu-id="4633b-179">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
