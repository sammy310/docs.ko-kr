---
title: <peerAuthentication> 요소
ms.date: 03/30/2017
ms.assetid: 09a8a9ff-e395-42f6-8ceb-9d44bdc1cbe1
ms.openlocfilehash: 093b0c4b6a7fbf54455ec523b52c1f3a9884cfa8
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90536017"
---
# <a name="peerauthentication-element"></a><span data-ttu-id="08c7e-102">\<peerAuthentication> 요소</span><span class="sxs-lookup"><span data-stu-id="08c7e-102">\<peerAuthentication> Element</span></span>
<span data-ttu-id="08c7e-103">피어 투 피어 클라이언트에 대한 인증 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="08c7e-103">Specifies authentication options for peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="08c7e-104">피어 투 피어 프로그래밍에 대 한 자세한 내용은 [피어 투 피어 네트워킹](../../../wcf/feature-details/peer-to-peer-networking.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="08c7e-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peerAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="08c7e-105">구문</span><span class="sxs-lookup"><span data-stu-id="08c7e-105">Syntax</span></span>  
  
```xml  
<peerAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                    certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                    revocationMode="NoCheck/Online/Offline"
                    trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="08c7e-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="08c7e-106">Attributes and Elements</span></span>  
 <span data-ttu-id="08c7e-107">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="08c7e-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="08c7e-108">특성</span><span class="sxs-lookup"><span data-stu-id="08c7e-108">Attributes</span></span>  
  
|<span data-ttu-id="08c7e-109">attribute</span><span class="sxs-lookup"><span data-stu-id="08c7e-109">Attribute</span></span>|<span data-ttu-id="08c7e-110">Description</span><span class="sxs-lookup"><span data-stu-id="08c7e-110">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="08c7e-111">선택적 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="08c7e-111">Optional string.</span></span> <span data-ttu-id="08c7e-112">사용자 지정 형식의 유효성을 검사하는 데 사용되는 형식 및 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="08c7e-112">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="08c7e-113">이 특성은 `certificateValidationMode`가 `Custom`으로 설정되어 있을 때 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08c7e-113">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="08c7e-114">선택적 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="08c7e-114">Optional enumeration.</span></span> <span data-ttu-id="08c7e-115">자격 증명의 유효성을 검사하는 데 사용되는 세 가지 모드 중 하나를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="08c7e-115">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="08c7e-116">`Custom`으로 설정되면 `customCertificateValidator`도 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08c7e-116">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="08c7e-117">기본값은 `ChainTrust`입니다.</span><span class="sxs-lookup"><span data-stu-id="08c7e-117">The default is `ChainTrust`.</span></span>|  
|`revocationMode`|<span data-ttu-id="08c7e-118">선택적 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="08c7e-118">Optional enumeration.</span></span> <span data-ttu-id="08c7e-119">CRL(해지된 인증서 목록)을 검사하는 데 사용되는 모드 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="08c7e-119">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="08c7e-120">기본값은 `Online`입니다.</span><span class="sxs-lookup"><span data-stu-id="08c7e-120">The default is `Online`.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="08c7e-121">선택적 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="08c7e-121">Optional enumeration.</span></span> <span data-ttu-id="08c7e-122">시스템 저장소 위치 `LocalMachine` 또는 `CurrentUser` 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="08c7e-122">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="08c7e-123">서비스 인증서가 클라이언트와 협상될 때 이 값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="08c7e-123">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="08c7e-124">지정 된 저장소 위치에 있는 **신뢰할 수 있는 사용자** 저장소에 대해 유효성 검사가 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08c7e-124">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="08c7e-125">기본값은 `CurrentUser`입니다.</span><span class="sxs-lookup"><span data-stu-id="08c7e-125">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="08c7e-126">customCertificateValidatorType 특성</span><span class="sxs-lookup"><span data-stu-id="08c7e-126">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="08c7e-127">값</span><span class="sxs-lookup"><span data-stu-id="08c7e-127">Value</span></span>|<span data-ttu-id="08c7e-128">Description</span><span class="sxs-lookup"><span data-stu-id="08c7e-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="08c7e-129">String</span><span class="sxs-lookup"><span data-stu-id="08c7e-129">String</span></span>|<span data-ttu-id="08c7e-130">형식 이름 및 어셈블리와 형식을 찾는 데 사용되는 기타 데이터를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="08c7e-130">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="08c7e-131">적어도 네임스페이스 및 형식 이름이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="08c7e-131">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="08c7e-132">선택적 정보로는 어셈블리 이름, 버전 번호, 문화권 및 공개 키 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08c7e-132">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="08c7e-133">certificateValidationMode 특성</span><span class="sxs-lookup"><span data-stu-id="08c7e-133">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="08c7e-134">값</span><span class="sxs-lookup"><span data-stu-id="08c7e-134">Value</span></span>|<span data-ttu-id="08c7e-135">Description</span><span class="sxs-lookup"><span data-stu-id="08c7e-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="08c7e-136">열거형</span><span class="sxs-lookup"><span data-stu-id="08c7e-136">Enumeration</span></span>|<span data-ttu-id="08c7e-137">`None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom` 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="08c7e-137">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="08c7e-138">기본값은 `ChainTrust`입니다.</span><span class="sxs-lookup"><span data-stu-id="08c7e-138">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="08c7e-139">자세한 내용은 [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="08c7e-139">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="08c7e-140">revocationMode 특성</span><span class="sxs-lookup"><span data-stu-id="08c7e-140">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="08c7e-141">값</span><span class="sxs-lookup"><span data-stu-id="08c7e-141">Value</span></span>|<span data-ttu-id="08c7e-142">Description</span><span class="sxs-lookup"><span data-stu-id="08c7e-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="08c7e-143">열거형</span><span class="sxs-lookup"><span data-stu-id="08c7e-143">Enumeration</span></span>|<span data-ttu-id="08c7e-144">`NoCheck`, `Online`, `Offline` 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="08c7e-144">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="08c7e-145">기본값은 `Online`입니다.</span><span class="sxs-lookup"><span data-stu-id="08c7e-145">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="08c7e-146">자세한 내용은 [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="08c7e-146">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="08c7e-147">trustedStoreLocation 특성</span><span class="sxs-lookup"><span data-stu-id="08c7e-147">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="08c7e-148">값</span><span class="sxs-lookup"><span data-stu-id="08c7e-148">Value</span></span>|<span data-ttu-id="08c7e-149">Description</span><span class="sxs-lookup"><span data-stu-id="08c7e-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="08c7e-150">열거형</span><span class="sxs-lookup"><span data-stu-id="08c7e-150">Enumeration</span></span>|<span data-ttu-id="08c7e-151">`LocalMachine` 또는 `CurrentUser` 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="08c7e-151">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="08c7e-152">기본값은 `CurrentUser`입니다.</span><span class="sxs-lookup"><span data-stu-id="08c7e-152">The default is `CurrentUser`.</span></span> <span data-ttu-id="08c7e-153">시스템 계정으로 클라이언트 애플리케이션을 실행하는 경우 인증서는 대개 `LocalMachine`에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08c7e-153">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="08c7e-154">사용자 계정으로 클라이언트 애플리케이션을 실행하는 경우 인증서는 대개 `CurrentUser`에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08c7e-154">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="08c7e-155">자식 요소</span><span class="sxs-lookup"><span data-stu-id="08c7e-155">Child Elements</span></span>  
 <span data-ttu-id="08c7e-156">없음</span><span class="sxs-lookup"><span data-stu-id="08c7e-156">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="08c7e-157">부모 요소</span><span class="sxs-lookup"><span data-stu-id="08c7e-157">Parent Elements</span></span>  
  
|<span data-ttu-id="08c7e-158">요소</span><span class="sxs-lookup"><span data-stu-id="08c7e-158">Element</span></span>|<span data-ttu-id="08c7e-159">Description</span><span class="sxs-lookup"><span data-stu-id="08c7e-159">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-clientcredentials-element.md)|<span data-ttu-id="08c7e-160">피어 서비스에 대해 클라이언트를 인증하는 데 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="08c7e-160">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08c7e-161">설명</span><span class="sxs-lookup"><span data-stu-id="08c7e-161">Remarks</span></span>  
 <span data-ttu-id="08c7e-162">`<authentication>` 요소는 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> 클래스에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="08c7e-162">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="08c7e-163">이 요소는 메시의 환경 간 인증 중에 호출되는 유효성 검사기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="08c7e-163">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="08c7e-164">새 피어는 환경 연결을 설정하려고 할 때 응답 피어에 해당 자격 증명을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="08c7e-164">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="08c7e-165">원격 상대방의 자격 증명의 유효성 검사를 위해 응답자의 유효성 검사기가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="08c7e-165">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="08c7e-166">메시에서 피어 연결이 설정될 때마다 두 피어는 상호 인증됩니다. 즉, 양쪽에서 유효성 검사기가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="08c7e-166">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="example"></a><span data-ttu-id="08c7e-167">예제</span><span class="sxs-lookup"><span data-stu-id="08c7e-167">Example</span></span>  
 <span data-ttu-id="08c7e-168">다음 코드에서는 인증서 유효성 검사 모드를 `PeerOrChainTrust`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="08c7e-168">The following code sets the certificate validation mode to `PeerOrChainTrust`.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <peer>
          <certificate findValue="www.contoso.com"
                       storeLocation="LocalMachine"
                       x509FindType="FindByIssuerName" />
          <peerAuthentication certificateValidationMode="PeerOrChainTrust" />
          <messageSenderAuthentication certificateValidationMode="None" />
        </peer>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="08c7e-169">참조</span><span class="sxs-lookup"><span data-stu-id="08c7e-169">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="08c7e-170">인증서 사용</span><span class="sxs-lookup"><span data-stu-id="08c7e-170">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="08c7e-171">피어 투 피어 네트워킹</span><span class="sxs-lookup"><span data-stu-id="08c7e-171">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="08c7e-172">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="08c7e-172">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="08c7e-173">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="08c7e-173">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="08c7e-174">피어 채널 애플리케이션 보안</span><span class="sxs-lookup"><span data-stu-id="08c7e-174">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
