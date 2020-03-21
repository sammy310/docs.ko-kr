---
title: <netMsmqBinding>의 <transport>
ms.date: 03/30/2017
ms.assetid: 72e1b338-39f0-4af1-a5d9-7a2fb79f6a0b
ms.openlocfilehash: cc47c01cccc931e81ba57ab37ad9e3accfaa693b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152933"
---
# <a name="transport-of-netmsmqbinding"></a><span data-ttu-id="b4ef1-102">\<\<netMsmq바인딩> 전송></span><span class="sxs-lookup"><span data-stu-id="b4ef1-102">\<transport> of \<netMsmqBinding></span></span>
<span data-ttu-id="b4ef1-103">전송 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b4ef1-103">Defines the transport security settings.</span></span>  
  
<span data-ttu-id="b4ef1-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b4ef1-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b4ef1-105">&nbsp;&nbsp;[**\<system.service모델>**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="b4ef1-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="b4ef1-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<바인딩>**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="b4ef1-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="b4ef1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmq바인딩>**](netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="b4ef1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)</span></span>\
<span data-ttu-id="b4ef1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<바인딩>**</span><span class="sxs-lookup"><span data-stu-id="b4ef1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="b4ef1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<보안>**](security-of-netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="b4ef1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netmsmqbinding.md)</span></span>\
<span data-ttu-id="b4ef1-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<운송>**</span><span class="sxs-lookup"><span data-stu-id="b4ef1-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4ef1-111">구문</span><span class="sxs-lookup"><span data-stu-id="b4ef1-111">Syntax</span></span>  
  
```xml  
<netMsmqBinding>
  <binding>
    <security>
      <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
                 msmqEncryptionAlgorithm="RC4Stream/AES"
                 msmqProtectionLevel="None/Sign/EncryptAndSign"
                 msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
    </security>
  </binding>
</netMsmqBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b4ef1-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b4ef1-112">Attributes and Elements</span></span>  
 <span data-ttu-id="b4ef1-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b4ef1-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b4ef1-114">특성</span><span class="sxs-lookup"><span data-stu-id="b4ef1-114">Attributes</span></span>  
  
|<span data-ttu-id="b4ef1-115">attribute</span><span class="sxs-lookup"><span data-stu-id="b4ef1-115">Attribute</span></span>|<span data-ttu-id="b4ef1-116">Description</span><span class="sxs-lookup"><span data-stu-id="b4ef1-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b4ef1-117">msmqAuthenticationMode</span><span class="sxs-lookup"><span data-stu-id="b4ef1-117">msmqAuthenticationMode</span></span>|<span data-ttu-id="b4ef1-118">메시지가 MSMQ 전송에 의해 인증되는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b4ef1-118">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="b4ef1-119">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b4ef1-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="b4ef1-120">- 없음: 인증 없음.</span><span class="sxs-lookup"><span data-stu-id="b4ef1-120">-   None: No authentication.</span></span><br /><span data-ttu-id="b4ef1-121">- WindowsDomain: 인증 메커니즘은 Active Directory를 사용하여 메시지와 연결된 보안 식별자에 대한 X.509 인증서를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="b4ef1-121">-   WindowsDomain: The authentication mechanism uses Active Directory to retrieve the X.509 certificate for the security identifier associated with the message.</span></span> <span data-ttu-id="b4ef1-122">그런 다음 이 인증서는 사용자에게 큐에 대한 쓰기 권한이 있는지 확인하기 위해 큐의 ACL을 검사하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4ef1-122">This is then used to check the ACL of the queue to ensure the user has write permission for the queue.</span></span><br /><span data-ttu-id="b4ef1-123">- 인증서 : 채널은 인증서 저장소에서 인증서를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="b4ef1-123">-   Certificate: The channel retrieves the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="b4ef1-124">기본값은 `WindowsDomain`입니다.</span><span class="sxs-lookup"><span data-stu-id="b4ef1-124">The default is `WindowsDomain`.</span></span><br /><br /> <span data-ttu-id="b4ef1-125">이 특성이 `None`으로 설정되면 `msmqProtectionLevel` 특성도 `None`으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4ef1-125">If this attribute is set to `None`, the `msmqProtectionLevel` attribute must also be set to `None`.</span></span> <span data-ttu-id="b4ef1-126">이 특성은 <xref:System.ServiceModel.MsmqAuthenticationMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b4ef1-126">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode></span></span>|  
|<span data-ttu-id="b4ef1-127">msmqEncryptionAlgorithm</span><span class="sxs-lookup"><span data-stu-id="b4ef1-127">msmqEncryptionAlgorithm</span></span>|<span data-ttu-id="b4ef1-128">메시지 큐 관리자 간에 메시지를 전송할 때 통신 중에 메시지 암호화에 사용할 알고리즘을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b4ef1-128">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="b4ef1-129">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b4ef1-129">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="b4ef1-130">- RC4Stream</span><span class="sxs-lookup"><span data-stu-id="b4ef1-130">-   RC4Stream</span></span><br /><span data-ttu-id="b4ef1-131">- AES</span><span class="sxs-lookup"><span data-stu-id="b4ef1-131">-   AES</span></span><br /><span data-ttu-id="b4ef1-132">- 기본값은 `RC4Stream`.</span><span class="sxs-lookup"><span data-stu-id="b4ef1-132">-   The default value is `RC4Stream`.</span></span> <span data-ttu-id="b4ef1-133">이 특성은 <xref:System.ServiceModel.MsmqEncryptionAlgorithm> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b4ef1-133">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|<span data-ttu-id="b4ef1-134">msmqProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="b4ef1-134">msmqProtectionLevel</span></span>|<span data-ttu-id="b4ef1-135">메시지가 MSMQ 전송 수준에서 보호되는 방식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b4ef1-135">Specifies the way messages are secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="b4ef1-136">암호화는 메시지 무결성을 보장하지만 서명 및 암호화는 메시지 무결성 및 부인 없음을 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="b4ef1-136">Encryption ensures message integrity, while sign and encrypt ensures both message integrity and non-repudiation.</span></span> <span data-ttu-id="b4ef1-137">즉, 메시지는 실제로 보낸 사람에서 왔고 보낸 사람은 그들이 말하는 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="b4ef1-137">That is, the message indeed came from the sender and the sender is who they say they are.</span></span> <span data-ttu-id="b4ef1-138">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b4ef1-138">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="b4ef1-139">- 없음: 보호 없음.</span><span class="sxs-lookup"><span data-stu-id="b4ef1-139">-   None: No protection.</span></span><br /><span data-ttu-id="b4ef1-140">- 서명 : 메시지가 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4ef1-140">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="b4ef1-141">- 암호화AndSign: 메시지가 암호화되고 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4ef1-141">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><span data-ttu-id="b4ef1-142">- 기본값은 `Sign`.</span><span class="sxs-lookup"><span data-stu-id="b4ef1-142">-   The default is `Sign`.</span></span>|  
|<span data-ttu-id="b4ef1-143">msmqSecureHashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="b4ef1-143">msmqSecureHashAlgorithm</span></span>|<span data-ttu-id="b4ef1-144">메시지 다이제스트를 계산하는 데 사용할 해시 알고리즘을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b4ef1-144">Specifies the hash algorithm to be used for computing the message digest.</span></span> <span data-ttu-id="b4ef1-145">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b4ef1-145">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="b4ef1-146">- MD5</span><span class="sxs-lookup"><span data-stu-id="b4ef1-146">-   MD5</span></span><br /><span data-ttu-id="b4ef1-147">- SHA1</span><span class="sxs-lookup"><span data-stu-id="b4ef1-147">-   SHA1</span></span><br /><span data-ttu-id="b4ef1-148">- SHA256</span><span class="sxs-lookup"><span data-stu-id="b4ef1-148">-   SHA256</span></span><br /><span data-ttu-id="b4ef1-149">- SHA512</span><span class="sxs-lookup"><span data-stu-id="b4ef1-149">-   SHA512</span></span><br /><br /> <span data-ttu-id="b4ef1-150">기본값은 `SHA1`입니다.</span><span class="sxs-lookup"><span data-stu-id="b4ef1-150">The default is `SHA1`.</span></span> <span data-ttu-id="b4ef1-151">이 특성은 <xref:System.ServiceModel.MsmqSecureHashAlgorithm> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b4ef1-151">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span><br><span data-ttu-id="b4ef1-152">MD5 및 SHA1과의 충돌 문제로 인해 SHA256 이상은 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4ef1-152">Due to collision problems with MD5 and SHA1, Microsoft recommends SHA256 or better.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b4ef1-153">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b4ef1-153">Child Elements</span></span>  
 <span data-ttu-id="b4ef1-154">None</span><span class="sxs-lookup"><span data-stu-id="b4ef1-154">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b4ef1-155">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b4ef1-155">Parent Elements</span></span>  
  
|<span data-ttu-id="b4ef1-156">요소</span><span class="sxs-lookup"><span data-stu-id="b4ef1-156">Element</span></span>|<span data-ttu-id="b4ef1-157">Description</span><span class="sxs-lookup"><span data-stu-id="b4ef1-157">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b4ef1-158">\<보안></span><span class="sxs-lookup"><span data-stu-id="b4ef1-158">\<security></span></span>](security-of-netmsmqbinding.md)|<span data-ttu-id="b4ef1-159">대기 중인 전송에 대한 전송 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b4ef1-159">Defines the transport security settings for queued transports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b4ef1-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b4ef1-160">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [<span data-ttu-id="b4ef1-161">WCF의 큐</span><span class="sxs-lookup"><span data-stu-id="b4ef1-161">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="b4ef1-162">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="b4ef1-162">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="b4ef1-163">바인딩</span><span class="sxs-lookup"><span data-stu-id="b4ef1-163">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b4ef1-164">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="b4ef1-164">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="b4ef1-165">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="b4ef1-165">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="b4ef1-166">\<바인딩></span><span class="sxs-lookup"><span data-stu-id="b4ef1-166">\<binding></span></span>](bindings.md)
