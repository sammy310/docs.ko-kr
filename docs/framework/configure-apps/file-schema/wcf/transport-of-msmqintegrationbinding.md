---
title: <msmqIntegrationBinding>의 <transport>
ms.date: 03/30/2017
ms.assetid: 054579e3-7fdd-47df-99ca-952706ba5c8e
ms.openlocfilehash: 859bc00557f66e27d7bd82a16704fc59c6044613
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934723"
---
# <a name="transport-of-msmqintegrationbinding"></a><span data-ttu-id="d3ec1-102">\<msmqIntegrationBinding >의 \<전송 ></span><span class="sxs-lookup"><span data-stu-id="d3ec1-102">\<transport> of \<msmqIntegrationBinding></span></span>
<span data-ttu-id="d3ec1-103">메시지 큐 통합 전송을 위한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-103">Defines the security settings for the Message Queuing integration transport.</span></span>  
  
 <span data-ttu-id="d3ec1-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d3ec1-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d3ec1-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="d3ec1-105">\<bindings></span></span>  
<span data-ttu-id="d3ec1-106">msmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="d3ec1-106">msmqIntegrationBinding</span></span>  
<span data-ttu-id="d3ec1-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="d3ec1-107">\<binding></span></span>  
<span data-ttu-id="d3ec1-108">\<security></span><span class="sxs-lookup"><span data-stu-id="d3ec1-108">\<security></span></span>  
<span data-ttu-id="d3ec1-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="d3ec1-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3ec1-110">구문</span><span class="sxs-lookup"><span data-stu-id="d3ec1-110">Syntax</span></span>  
  
```xml  
<security>
  <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
             msmqEncryptionAlgorithm="RC4Stream/AES"
             msmqProtectionLevel="None/Sign/EncryptAndSign"
             msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d3ec1-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d3ec1-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d3ec1-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d3ec1-113">특성</span><span class="sxs-lookup"><span data-stu-id="d3ec1-113">Attributes</span></span>  
  
|<span data-ttu-id="d3ec1-114">특성</span><span class="sxs-lookup"><span data-stu-id="d3ec1-114">Attribute</span></span>|<span data-ttu-id="d3ec1-115">Description</span><span class="sxs-lookup"><span data-stu-id="d3ec1-115">Description</span></span>|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|<span data-ttu-id="d3ec1-116">메시지가 MSMQ 전송에 의해 인증되는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-116">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="d3ec1-117">이 특성이 `None`으로 설정되면 `msmqProtectionLevel` 특성 값도 `None`으로 설정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-117">If this is set to `None`, the value of the `msmqProtectionLevel` attribute must also be set to `None`.</span></span><br /><br /> <span data-ttu-id="d3ec1-118">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="d3ec1-119">없음을 인증 안 함.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-119">-   None: No authentication.</span></span><br /><span data-ttu-id="d3ec1-120">-   WindowsDomain: 인증 메커니즘은 Active Directory를 사용 하 여 메시지와 연결 된 SID에 대 한 x.509 인증서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-120">-   WindowsDomain: The authentication mechanism uses Active Directory to get the X.509 certificate for the SID associated with the message.</span></span> <span data-ttu-id="d3ec1-121">그런 다음 이 인증서는 사용자에게 큐에 대한 쓰기 권한이 있는지 확인하기 위해 큐의 ACL을 검사하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-121">This is then used to check the ACL of the queue to ensure the user has permission to write to the queue.</span></span><br /><span data-ttu-id="d3ec1-122">인증서 채널이 인증서 저장소에서 인증서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-122">-   Certificate: The channel gets the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="d3ec1-123">기본값은 WindowsDomain입니다.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-123">The default value is WindowsDomain.</span></span> <span data-ttu-id="d3ec1-124">이 특성은 <xref:System.ServiceModel.MsmqAuthenticationMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-124">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode>.</span></span>|  
|`msmqEncryptionAlgorithm`|<span data-ttu-id="d3ec1-125">메시지 큐 관리자 간에 메시지를 전송할 때 통신 중에 메시지 암호화에 사용할 알고리즘을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-125">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="d3ec1-126">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="d3ec1-127">-   RC4Stream</span><span class="sxs-lookup"><span data-stu-id="d3ec1-127">-   RC4Stream</span></span><br /><span data-ttu-id="d3ec1-128">-   AES</span><span class="sxs-lookup"><span data-stu-id="d3ec1-128">-   AES</span></span><br /><br /> <span data-ttu-id="d3ec1-129">기본값은 RC4Stream입니다.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-129">The default value is RC4Stream.</span></span> <span data-ttu-id="d3ec1-130">이 특성은 <xref:System.ServiceModel.MsmqEncryptionAlgorithm> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-130">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|`msmqProtectionLevel`|<span data-ttu-id="d3ec1-131">메시지가 MSMQ 전송 수준에서 보호되는 방식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-131">Specifies how the message is secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="d3ec1-132">EncryptAndSign이 메시지 무결성 및 비부인을 보장하는 반면 암호화는 메시지 무결성을 보장합니다. 즉, 메시지는 실제로 보낸 사람으로부터 나오고 보낸 사람은 보낸 사람임을 밝히는 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-132">Encryption ensures message integrity while EncryptAndSign ensures both message integrity and non-repudiation; that is, the message indeed comes from the sender and the sender is who he says he is.</span></span><br /><br /> <span data-ttu-id="d3ec1-133">-유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-133">-   Valid values include the following:</span></span><br /><span data-ttu-id="d3ec1-134">없음을 보호되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-134">-   None: No protection.</span></span><br /><span data-ttu-id="d3ec1-135">로그인 메시지가 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-135">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="d3ec1-136">-   EncryptAndSign: 메시지가 암호화되고 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-136">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="d3ec1-137">기본값은 Sign입니다.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-137">The default value is Sign.</span></span> <span data-ttu-id="d3ec1-138">이 특성은 ProtectionLevel 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-138">This attribute is of type ProtectionLevel.</span></span>|  
|`msmqSecureHashAlgorithm`|<span data-ttu-id="d3ec1-139">-시그니처의 일부로 다이제스트를 계산 하는 데 사용할 알고리즘을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-139">-   Specifies the algorithm to be used in computing the digest as part of signatures.</span></span> <span data-ttu-id="d3ec1-140">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-140">Valid values include the following:</span></span><br /><span data-ttu-id="d3ec1-141">-   MD5</span><span class="sxs-lookup"><span data-stu-id="d3ec1-141">-   MD5</span></span><br /><span data-ttu-id="d3ec1-142">-   SHA1</span><span class="sxs-lookup"><span data-stu-id="d3ec1-142">-   SHA1</span></span><br /><span data-ttu-id="d3ec1-143">-   SHA256</span><span class="sxs-lookup"><span data-stu-id="d3ec1-143">-   SHA256</span></span><br /><span data-ttu-id="d3ec1-144">-   SHA512</span><span class="sxs-lookup"><span data-stu-id="d3ec1-144">-   SHA512</span></span><br /><br /> <span data-ttu-id="d3ec1-145">기본값은 SHA1입니다.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-145">The default value is SHA1.</span></span> <span data-ttu-id="d3ec1-146">이 특성은 <xref:System.ServiceModel.MsmqSecureHashAlgorithm> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-146">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span><br><span data-ttu-id="d3ec1-147">MD5 및 s h a 1의 충돌 문제로 인해 s h a 1 이상을 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-147">Due to collision problems with MD5 and SHA1, Microsoft recommends SHA256 or better.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d3ec1-148">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d3ec1-148">Child Elements</span></span>  
 <span data-ttu-id="d3ec1-149">없음</span><span class="sxs-lookup"><span data-stu-id="d3ec1-149">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d3ec1-150">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d3ec1-150">Parent Elements</span></span>  
  
|<span data-ttu-id="d3ec1-151">요소</span><span class="sxs-lookup"><span data-stu-id="d3ec1-151">Element</span></span>|<span data-ttu-id="d3ec1-152">설명</span><span class="sxs-lookup"><span data-stu-id="d3ec1-152">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d3ec1-153">\<security></span><span class="sxs-lookup"><span data-stu-id="d3ec1-153">\<security></span></span>](security-of-basichttpbinding.md)|<span data-ttu-id="d3ec1-154">MSMQ 바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-154">Defines the security settings for a MSMQ binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3ec1-155">설명</span><span class="sxs-lookup"><span data-stu-id="d3ec1-155">Remarks</span></span>  
 <span data-ttu-id="d3ec1-156">이 요소는 메시지 큐 통합 전송을 위한 보안 설정을 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-156">This element encapsulates the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="d3ec1-157">설정은 메시지 큐 통합 및 대기 중인 전송에서 모두 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-157">The settings are the same for both the Message Queuing integration and queued transports.</span></span> <span data-ttu-id="d3ec1-158">이 요소를 사용하여 인증 모드, 암호화 알고리즘, 보안 해시 알고리즘 및 보호 수준을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ec1-158">It enables you to set the Authentication Mode, Encryption Algorithm, Secure Hash Algorithm, and Protection Level.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3ec1-159">참고자료</span><span class="sxs-lookup"><span data-stu-id="d3ec1-159">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [<span data-ttu-id="d3ec1-160">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="d3ec1-160">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="d3ec1-161">바인딩</span><span class="sxs-lookup"><span data-stu-id="d3ec1-161">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d3ec1-162">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="d3ec1-162">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="d3ec1-163">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="d3ec1-163">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="d3ec1-164">\<binding></span><span class="sxs-lookup"><span data-stu-id="d3ec1-164">\<binding></span></span>](../../../misc/binding.md)
