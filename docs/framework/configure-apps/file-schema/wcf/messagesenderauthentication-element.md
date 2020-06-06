---
title: <messageSenderAuthentication> 요소
ms.date: 03/30/2017
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
ms.openlocfilehash: bab0e50d7feba3ea55d505be07cfa41427a5cbbc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397784"
---
# <a name="messagesenderauthentication-element"></a><span data-ttu-id="1ebd6-102">\<messageSenderAuthentication> 요소</span><span class="sxs-lookup"><span data-stu-id="1ebd6-102">\<messageSenderAuthentication> element</span></span>
<span data-ttu-id="1ebd6-103">피어 투 피어 메시지 발신자에 대한 인증 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1ebd6-103">Specifies authentication options for peer-to-peer message senders.</span></span>  
  
 <span data-ttu-id="1ebd6-104">피어 투 피어 프로그래밍에 대 한 자세한 내용은 [피어 투 피어 네트워킹](../../../wcf/feature-details/peer-to-peer-networking.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1ebd6-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<messageSenderAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="1ebd6-105">구문</span><span class="sxs-lookup"><span data-stu-id="1ebd6-105">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1ebd6-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1ebd6-106">Attributes and Elements</span></span>  
 <span data-ttu-id="1ebd6-107">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1ebd6-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1ebd6-108">특성</span><span class="sxs-lookup"><span data-stu-id="1ebd6-108">Attributes</span></span>  
  
|<span data-ttu-id="1ebd6-109">attribute</span><span class="sxs-lookup"><span data-stu-id="1ebd6-109">Attribute</span></span>|<span data-ttu-id="1ebd6-110">Description</span><span class="sxs-lookup"><span data-stu-id="1ebd6-110">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="1ebd6-111">사용자 지정 형식의 유효성을 검사하는 데 사용되는 형식 및 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="1ebd6-111">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="1ebd6-112">이 특성은 `certificateValidationMode`가 `Custom`으로 설정되어 있을 때 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ebd6-112">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="1ebd6-113">자격 증명의 유효성을 검사하는 데 사용되는 세 가지 모드 중 하나를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1ebd6-113">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="1ebd6-114">`Custom`으로 설정되면 `customCertificateValidator`도 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ebd6-114">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`revocationMode`|<span data-ttu-id="1ebd6-115">CRL(해지된 인증서 목록)을 검사하는 데 사용되는 모드 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="1ebd6-115">One of the modes used to check for a revoked certificate lists (CRL).</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="1ebd6-116">시스템 저장소 위치 `LocalMachine` 또는 `CurrentUser` 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="1ebd6-116">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="1ebd6-117">서비스 인증서가 클라이언트와 협상될 때 이 값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ebd6-117">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="1ebd6-118">지정 된 저장소 위치에 있는 **신뢰할 수 있는 사용자** 저장소에 대해 유효성 검사가 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ebd6-118">Validation is performed against the **Trusted People** store in the specified store location.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="1ebd6-119">customCertificateValidatorType 특성</span><span class="sxs-lookup"><span data-stu-id="1ebd6-119">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="1ebd6-120">값</span><span class="sxs-lookup"><span data-stu-id="1ebd6-120">Value</span></span>|<span data-ttu-id="1ebd6-121">Description</span><span class="sxs-lookup"><span data-stu-id="1ebd6-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1ebd6-122">문자열</span><span class="sxs-lookup"><span data-stu-id="1ebd6-122">String</span></span>|<span data-ttu-id="1ebd6-123">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="1ebd6-123">Optional.</span></span> <span data-ttu-id="1ebd6-124">형식 이름 및 어셈블리와 형식을 찾는 데 사용되는 기타 데이터를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1ebd6-124">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="1ebd6-125">적어도 네임스페이스 및 형식 이름이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1ebd6-125">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="1ebd6-126">선택적 정보로는 어셈블리 이름, 버전 번호, 문화권 및 공개 키 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ebd6-126">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="1ebd6-127">certificateValidationMode 특성</span><span class="sxs-lookup"><span data-stu-id="1ebd6-127">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="1ebd6-128">값</span><span class="sxs-lookup"><span data-stu-id="1ebd6-128">Value</span></span>|<span data-ttu-id="1ebd6-129">Description</span><span class="sxs-lookup"><span data-stu-id="1ebd6-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1ebd6-130">열거형</span><span class="sxs-lookup"><span data-stu-id="1ebd6-130">Enumeration</span></span>|<span data-ttu-id="1ebd6-131">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="1ebd6-131">Optional.</span></span> <span data-ttu-id="1ebd6-132">`None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom` 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="1ebd6-132">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="1ebd6-133">기본값은 `ChainTrust`입니다.</span><span class="sxs-lookup"><span data-stu-id="1ebd6-133">The default is `ChainTrust`.</span></span> <span data-ttu-id="1ebd6-134">기본값은 `ChainTrust`입니다.</span><span class="sxs-lookup"><span data-stu-id="1ebd6-134">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="1ebd6-135">자세한 내용은 [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1ebd6-135">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="1ebd6-136">revocationMode 특성</span><span class="sxs-lookup"><span data-stu-id="1ebd6-136">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="1ebd6-137">값</span><span class="sxs-lookup"><span data-stu-id="1ebd6-137">Value</span></span>|<span data-ttu-id="1ebd6-138">Description</span><span class="sxs-lookup"><span data-stu-id="1ebd6-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1ebd6-139">열거형</span><span class="sxs-lookup"><span data-stu-id="1ebd6-139">Enumeration</span></span>|<span data-ttu-id="1ebd6-140">`NoCheck`, `Online`, `Offline` 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="1ebd6-140">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="1ebd6-141">기본값은 `Online`입니다.</span><span class="sxs-lookup"><span data-stu-id="1ebd6-141">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="1ebd6-142">자세한 내용은 [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1ebd6-142">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="1ebd6-143">trustedStoreLocation 특성</span><span class="sxs-lookup"><span data-stu-id="1ebd6-143">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="1ebd6-144">값</span><span class="sxs-lookup"><span data-stu-id="1ebd6-144">Value</span></span>|<span data-ttu-id="1ebd6-145">Description</span><span class="sxs-lookup"><span data-stu-id="1ebd6-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1ebd6-146">열거형</span><span class="sxs-lookup"><span data-stu-id="1ebd6-146">Enumeration</span></span>|<span data-ttu-id="1ebd6-147">`LocalMachine` 또는 `CurrentUser` 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="1ebd6-147">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="1ebd6-148">기본값은 `CurrentUser`입니다.</span><span class="sxs-lookup"><span data-stu-id="1ebd6-148">The default is `CurrentUser`.</span></span> <span data-ttu-id="1ebd6-149">시스템 계정으로 클라이언트 애플리케이션을 실행하는 경우 인증서는 대개 `LocalMachine`에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ebd6-149">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="1ebd6-150">사용자 계정으로 클라이언트 애플리케이션을 실행하는 경우 인증서는 대개 `CurrentUser`에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ebd6-150">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span> <span data-ttu-id="1ebd6-151">기본값은 `CurrentUser`입니다.</span><span class="sxs-lookup"><span data-stu-id="1ebd6-151">The default is `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1ebd6-152">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1ebd6-152">Child Elements</span></span>  
 <span data-ttu-id="1ebd6-153">없음</span><span class="sxs-lookup"><span data-stu-id="1ebd6-153">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1ebd6-154">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1ebd6-154">Parent Elements</span></span>  
  
|<span data-ttu-id="1ebd6-155">요소</span><span class="sxs-lookup"><span data-stu-id="1ebd6-155">Element</span></span>|<span data-ttu-id="1ebd6-156">Description</span><span class="sxs-lookup"><span data-stu-id="1ebd6-156">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-clientcredentials-element.md)|<span data-ttu-id="1ebd6-157">피어 서비스에 대해 클라이언트를 인증하는 데 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1ebd6-157">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ebd6-158">설명</span><span class="sxs-lookup"><span data-stu-id="1ebd6-158">Remarks</span></span>  
 <span data-ttu-id="1ebd6-159">메시지 인증을 선택하면 이 요소를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ebd6-159">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="1ebd6-160">출력 채널의 경우 각 메시지는에서 제공 하는 인증서를 사용 하 여 서명 됩니다 [\<certificate>](certificate-element.md) .</span><span class="sxs-lookup"><span data-stu-id="1ebd6-160">For output channels, each message is signed using the certificate provided by [\<certificate>](certificate-element.md).</span></span> <span data-ttu-id="1ebd6-161">모든 메시지는 애플리케이션에 배달되기 전에 이 요소의 `customCertificateValidatorType` 특성에 지정된 유효성 검사기를 사용하여 메시지 자격 증명과 비교하여 검사됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ebd6-161">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="1ebd6-162">유효성 검사기는 자격 증명을 수락하거나 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ebd6-162">The validator can either accept or reject the credential.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ebd6-163">예제</span><span class="sxs-lookup"><span data-stu-id="1ebd6-163">Example</span></span>  
 <span data-ttu-id="1ebd6-164">다음 코드에서는 메시지 발신자 유효성 검사 모드를 `PeerOrChainTrust`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1ebd6-164">The following code sets the message sender validation mode to `PeerOrChainTrust`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1ebd6-165">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1ebd6-165">See also</span></span>

- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="1ebd6-166">인증서 사용</span><span class="sxs-lookup"><span data-stu-id="1ebd6-166">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="1ebd6-167">피어 투 피어 네트워킹</span><span class="sxs-lookup"><span data-stu-id="1ebd6-167">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="1ebd6-168">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="1ebd6-168">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="1ebd6-169">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="1ebd6-169">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="1ebd6-170">피어 채널 애플리케이션 보안</span><span class="sxs-lookup"><span data-stu-id="1ebd6-170">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
