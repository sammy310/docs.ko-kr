---
description: '다음에 대 한 자세한 정보: <messageSenderAuthentication> 요소'
title: <messageSenderAuthentication> 요소
ms.date: 03/30/2017
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
ms.openlocfilehash: 03c1cd626e7c3ad71026c076df3d757419810d74
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749339"
---
# <a name="messagesenderauthentication-element"></a><span data-ttu-id="eab0b-103">\<messageSenderAuthentication> 요소</span><span class="sxs-lookup"><span data-stu-id="eab0b-103">\<messageSenderAuthentication> element</span></span>

<span data-ttu-id="eab0b-104">피어 투 피어 메시지 발신자에 대한 인증 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eab0b-104">Specifies authentication options for peer-to-peer message senders.</span></span>  
  
 <span data-ttu-id="eab0b-105">피어 투 피어 프로그래밍에 대 한 자세한 내용은 [피어 투 피어 네트워킹](../../../wcf/feature-details/peer-to-peer-networking.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="eab0b-105">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<messageSenderAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="eab0b-106">구문</span><span class="sxs-lookup"><span data-stu-id="eab0b-106">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eab0b-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="eab0b-107">Attributes and Elements</span></span>  

 <span data-ttu-id="eab0b-108">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eab0b-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eab0b-109">특성</span><span class="sxs-lookup"><span data-stu-id="eab0b-109">Attributes</span></span>  
  
|<span data-ttu-id="eab0b-110">attribute</span><span class="sxs-lookup"><span data-stu-id="eab0b-110">Attribute</span></span>|<span data-ttu-id="eab0b-111">설명</span><span class="sxs-lookup"><span data-stu-id="eab0b-111">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="eab0b-112">사용자 지정 형식의 유효성을 검사하는 데 사용되는 형식 및 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="eab0b-112">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="eab0b-113">이 특성은 `certificateValidationMode`가 `Custom`으로 설정되어 있을 때 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eab0b-113">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="eab0b-114">자격 증명의 유효성을 검사하는 데 사용되는 세 가지 모드 중 하나를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eab0b-114">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="eab0b-115">`Custom`으로 설정되면 `customCertificateValidator`도 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eab0b-115">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`revocationMode`|<span data-ttu-id="eab0b-116">CRL(해지된 인증서 목록)을 검사하는 데 사용되는 모드 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="eab0b-116">One of the modes used to check for a revoked certificate lists (CRL).</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="eab0b-117">시스템 저장소 위치 `LocalMachine` 또는 `CurrentUser` 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="eab0b-117">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="eab0b-118">서비스 인증서가 클라이언트와 협상될 때 이 값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="eab0b-118">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="eab0b-119">지정 된 저장소 위치에 있는 **신뢰할 수 있는 사용자** 저장소에 대해 유효성 검사가 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eab0b-119">Validation is performed against the **Trusted People** store in the specified store location.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="eab0b-120">customCertificateValidatorType 특성</span><span class="sxs-lookup"><span data-stu-id="eab0b-120">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="eab0b-121">값</span><span class="sxs-lookup"><span data-stu-id="eab0b-121">Value</span></span>|<span data-ttu-id="eab0b-122">Description</span><span class="sxs-lookup"><span data-stu-id="eab0b-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="eab0b-123">String</span><span class="sxs-lookup"><span data-stu-id="eab0b-123">String</span></span>|<span data-ttu-id="eab0b-124">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="eab0b-124">Optional.</span></span> <span data-ttu-id="eab0b-125">형식 이름 및 어셈블리와 형식을 찾는 데 사용되는 기타 데이터를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eab0b-125">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="eab0b-126">적어도 네임스페이스 및 형식 이름이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="eab0b-126">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="eab0b-127">선택적 정보로는 어셈블리 이름, 버전 번호, 문화권 및 공개 키 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eab0b-127">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="eab0b-128">certificateValidationMode 특성</span><span class="sxs-lookup"><span data-stu-id="eab0b-128">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="eab0b-129">값</span><span class="sxs-lookup"><span data-stu-id="eab0b-129">Value</span></span>|<span data-ttu-id="eab0b-130">설명</span><span class="sxs-lookup"><span data-stu-id="eab0b-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="eab0b-131">열거형</span><span class="sxs-lookup"><span data-stu-id="eab0b-131">Enumeration</span></span>|<span data-ttu-id="eab0b-132">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="eab0b-132">Optional.</span></span> <span data-ttu-id="eab0b-133">`None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom` 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="eab0b-133">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="eab0b-134">기본값은 `ChainTrust`입니다.</span><span class="sxs-lookup"><span data-stu-id="eab0b-134">The default is `ChainTrust`.</span></span> <span data-ttu-id="eab0b-135">기본값은 `ChainTrust`입니다.</span><span class="sxs-lookup"><span data-stu-id="eab0b-135">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="eab0b-136">자세한 내용은 [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eab0b-136">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="eab0b-137">revocationMode 특성</span><span class="sxs-lookup"><span data-stu-id="eab0b-137">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="eab0b-138">값</span><span class="sxs-lookup"><span data-stu-id="eab0b-138">Value</span></span>|<span data-ttu-id="eab0b-139">설명</span><span class="sxs-lookup"><span data-stu-id="eab0b-139">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="eab0b-140">열거형</span><span class="sxs-lookup"><span data-stu-id="eab0b-140">Enumeration</span></span>|<span data-ttu-id="eab0b-141">`NoCheck`, `Online`, `Offline` 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="eab0b-141">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="eab0b-142">기본값은 `Online`입니다.</span><span class="sxs-lookup"><span data-stu-id="eab0b-142">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="eab0b-143">자세한 내용은 [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eab0b-143">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="eab0b-144">trustedStoreLocation 특성</span><span class="sxs-lookup"><span data-stu-id="eab0b-144">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="eab0b-145">값</span><span class="sxs-lookup"><span data-stu-id="eab0b-145">Value</span></span>|<span data-ttu-id="eab0b-146">설명</span><span class="sxs-lookup"><span data-stu-id="eab0b-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="eab0b-147">열거형</span><span class="sxs-lookup"><span data-stu-id="eab0b-147">Enumeration</span></span>|<span data-ttu-id="eab0b-148">`LocalMachine` 또는 `CurrentUser` 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="eab0b-148">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="eab0b-149">기본값은 `CurrentUser`입니다.</span><span class="sxs-lookup"><span data-stu-id="eab0b-149">The default is `CurrentUser`.</span></span> <span data-ttu-id="eab0b-150">시스템 계정으로 클라이언트 애플리케이션을 실행하는 경우 인증서는 대개 `LocalMachine`에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eab0b-150">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="eab0b-151">사용자 계정으로 클라이언트 애플리케이션을 실행하는 경우 인증서는 대개 `CurrentUser`에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eab0b-151">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span> <span data-ttu-id="eab0b-152">기본값은 `CurrentUser`입니다.</span><span class="sxs-lookup"><span data-stu-id="eab0b-152">The default is `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eab0b-153">자식 요소</span><span class="sxs-lookup"><span data-stu-id="eab0b-153">Child Elements</span></span>  

 <span data-ttu-id="eab0b-154">없음</span><span class="sxs-lookup"><span data-stu-id="eab0b-154">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eab0b-155">부모 요소</span><span class="sxs-lookup"><span data-stu-id="eab0b-155">Parent Elements</span></span>  
  
|<span data-ttu-id="eab0b-156">요소</span><span class="sxs-lookup"><span data-stu-id="eab0b-156">Element</span></span>|<span data-ttu-id="eab0b-157">설명</span><span class="sxs-lookup"><span data-stu-id="eab0b-157">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-clientcredentials-element.md)|<span data-ttu-id="eab0b-158">피어 서비스에 대해 클라이언트를 인증하는 데 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eab0b-158">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eab0b-159">설명</span><span class="sxs-lookup"><span data-stu-id="eab0b-159">Remarks</span></span>  

 <span data-ttu-id="eab0b-160">메시지 인증을 선택하면 이 요소를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eab0b-160">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="eab0b-161">출력 채널의 경우 각 메시지는에서 제공 하는 인증서를 사용 하 여 서명 됩니다 [\<certificate>](certificate-element.md) .</span><span class="sxs-lookup"><span data-stu-id="eab0b-161">For output channels, each message is signed using the certificate provided by [\<certificate>](certificate-element.md).</span></span> <span data-ttu-id="eab0b-162">모든 메시지는 애플리케이션에 배달되기 전에 이 요소의 `customCertificateValidatorType` 특성에 지정된 유효성 검사기를 사용하여 메시지 자격 증명과 비교하여 검사됩니다.</span><span class="sxs-lookup"><span data-stu-id="eab0b-162">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="eab0b-163">유효성 검사기는 자격 증명을 수락하거나 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eab0b-163">The validator can either accept or reject the credential.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eab0b-164">예제</span><span class="sxs-lookup"><span data-stu-id="eab0b-164">Example</span></span>  

 <span data-ttu-id="eab0b-165">다음 코드에서는 메시지 발신자 유효성 검사 모드를 `PeerOrChainTrust`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="eab0b-165">The following code sets the message sender validation mode to `PeerOrChainTrust`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="eab0b-166">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eab0b-166">See also</span></span>

- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="eab0b-167">인증서 사용</span><span class="sxs-lookup"><span data-stu-id="eab0b-167">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="eab0b-168">피어 투 피어 네트워킹</span><span class="sxs-lookup"><span data-stu-id="eab0b-168">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="eab0b-169">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="eab0b-169">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="eab0b-170">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="eab0b-170">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="eab0b-171">피어 채널 애플리케이션 보안</span><span class="sxs-lookup"><span data-stu-id="eab0b-171">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
