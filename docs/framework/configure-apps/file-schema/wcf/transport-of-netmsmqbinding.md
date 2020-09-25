---
title: <netMsmqBinding>의 <transport>
ms.date: 03/30/2017
ms.assetid: 72e1b338-39f0-4af1-a5d9-7a2fb79f6a0b
ms.openlocfilehash: 84a5437de851ecdb96d0463ec574186ba5f91d9e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203880"
---
# <a name="transport-of-netmsmqbinding"></a><span data-ttu-id="b47f2-102">\<netMsmqBinding>의 \<transport></span><span class="sxs-lookup"><span data-stu-id="b47f2-102">\<transport> of \<netMsmqBinding></span></span>

<span data-ttu-id="b47f2-103">전송 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b47f2-103">Defines the transport security settings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="b47f2-104">구문</span><span class="sxs-lookup"><span data-stu-id="b47f2-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b47f2-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b47f2-105">Attributes and Elements</span></span>  

 <span data-ttu-id="b47f2-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b47f2-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b47f2-107">특성</span><span class="sxs-lookup"><span data-stu-id="b47f2-107">Attributes</span></span>  
  
|<span data-ttu-id="b47f2-108">attribute</span><span class="sxs-lookup"><span data-stu-id="b47f2-108">Attribute</span></span>|<span data-ttu-id="b47f2-109">설명</span><span class="sxs-lookup"><span data-stu-id="b47f2-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b47f2-110">msmqAuthenticationMode</span><span class="sxs-lookup"><span data-stu-id="b47f2-110">msmqAuthenticationMode</span></span>|<span data-ttu-id="b47f2-111">메시지가 MSMQ 전송에 의해 인증되는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b47f2-111">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="b47f2-112">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b47f2-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="b47f2-113">-없음: 인증 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b47f2-113">-   None: No authentication.</span></span><br /><span data-ttu-id="b47f2-114">-WindowsDomain:이 인증 메커니즘은 Active Directory를 사용 하 여 메시지와 연결 된 보안 식별자에 대 한 x.509 인증서를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="b47f2-114">-   WindowsDomain: The authentication mechanism uses Active Directory to retrieve the X.509 certificate for the security identifier associated with the message.</span></span> <span data-ttu-id="b47f2-115">그런 다음 이 인증서는 사용자에게 큐에 대한 쓰기 권한이 있는지 확인하기 위해 큐의 ACL을 검사하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b47f2-115">This is then used to check the ACL of the queue to ensure the user has write permission for the queue.</span></span><br /><span data-ttu-id="b47f2-116">-Certificate: 채널은 인증서 저장소에서 인증서를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="b47f2-116">-   Certificate: The channel retrieves the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="b47f2-117">기본값은 `WindowsDomain`입니다.</span><span class="sxs-lookup"><span data-stu-id="b47f2-117">The default is `WindowsDomain`.</span></span><br /><br /> <span data-ttu-id="b47f2-118">이 특성이 `None`으로 설정되면 `msmqProtectionLevel` 특성도 `None`으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b47f2-118">If this attribute is set to `None`, the `msmqProtectionLevel` attribute must also be set to `None`.</span></span> <span data-ttu-id="b47f2-119">이 특성은 <xref:System.ServiceModel.MsmqAuthenticationMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b47f2-119">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode></span></span>|  
|<span data-ttu-id="b47f2-120">msmqEncryptionAlgorithm</span><span class="sxs-lookup"><span data-stu-id="b47f2-120">msmqEncryptionAlgorithm</span></span>|<span data-ttu-id="b47f2-121">메시지 큐 관리자 간에 메시지를 전송할 때 통신 중에 메시지 암호화에 사용할 알고리즘을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b47f2-121">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="b47f2-122">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b47f2-122">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="b47f2-123">-RC4Stream</span><span class="sxs-lookup"><span data-stu-id="b47f2-123">-   RC4Stream</span></span><br /><span data-ttu-id="b47f2-124">-AES</span><span class="sxs-lookup"><span data-stu-id="b47f2-124">-   AES</span></span><br /><span data-ttu-id="b47f2-125">-기본값은 `RC4Stream` 입니다.</span><span class="sxs-lookup"><span data-stu-id="b47f2-125">-   The default value is `RC4Stream`.</span></span> <span data-ttu-id="b47f2-126">이 특성은 <xref:System.ServiceModel.MsmqEncryptionAlgorithm> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b47f2-126">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|<span data-ttu-id="b47f2-127">msmqProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="b47f2-127">msmqProtectionLevel</span></span>|<span data-ttu-id="b47f2-128">메시지가 MSMQ 전송 수준에서 보호되는 방식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b47f2-128">Specifies the way messages are secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="b47f2-129">암호화는 메시지 무결성을 보장하지만 서명 및 암호화는 메시지 무결성 및 부인 없음을 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="b47f2-129">Encryption ensures message integrity, while sign and encrypt ensures both message integrity and non-repudiation.</span></span> <span data-ttu-id="b47f2-130">즉, 메시지는 보낸 사람이 보낸 메시지 이며 보낸 사람이 보낸 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="b47f2-130">That is, the message indeed came from the sender and the sender is who they say they are.</span></span> <span data-ttu-id="b47f2-131">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b47f2-131">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="b47f2-132">-없음: 보호 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b47f2-132">-   None: No protection.</span></span><br /><span data-ttu-id="b47f2-133">-서명: 메시지가 서명 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b47f2-133">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="b47f2-134">-EncryptAndSign: 메시지가 암호화 되 고 서명 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b47f2-134">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><span data-ttu-id="b47f2-135">-기본값은 `Sign` 입니다.</span><span class="sxs-lookup"><span data-stu-id="b47f2-135">-   The default is `Sign`.</span></span>|  
|<span data-ttu-id="b47f2-136">msmqSecureHashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="b47f2-136">msmqSecureHashAlgorithm</span></span>|<span data-ttu-id="b47f2-137">메시지 다이제스트를 계산하는 데 사용할 해시 알고리즘을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b47f2-137">Specifies the hash algorithm to be used for computing the message digest.</span></span> <span data-ttu-id="b47f2-138">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b47f2-138">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="b47f2-139">-MD5</span><span class="sxs-lookup"><span data-stu-id="b47f2-139">-   MD5</span></span><br /><span data-ttu-id="b47f2-140">-SHA1</span><span class="sxs-lookup"><span data-stu-id="b47f2-140">-   SHA1</span></span><br /><span data-ttu-id="b47f2-141">-SHA256</span><span class="sxs-lookup"><span data-stu-id="b47f2-141">-   SHA256</span></span><br /><span data-ttu-id="b47f2-142">-SHA512</span><span class="sxs-lookup"><span data-stu-id="b47f2-142">-   SHA512</span></span><br /><br /> <span data-ttu-id="b47f2-143">기본값은 `SHA1`입니다.</span><span class="sxs-lookup"><span data-stu-id="b47f2-143">The default is `SHA1`.</span></span> <span data-ttu-id="b47f2-144">이 특성은 <xref:System.ServiceModel.MsmqSecureHashAlgorithm> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b47f2-144">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span><br><span data-ttu-id="b47f2-145">MD5 및 s h a 1의 충돌 문제로 인해 s h a 1 이상을 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b47f2-145">Due to collision problems with MD5 and SHA1, Microsoft recommends SHA256 or better.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b47f2-146">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b47f2-146">Child Elements</span></span>  

 <span data-ttu-id="b47f2-147">없음</span><span class="sxs-lookup"><span data-stu-id="b47f2-147">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b47f2-148">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b47f2-148">Parent Elements</span></span>  
  
|<span data-ttu-id="b47f2-149">요소</span><span class="sxs-lookup"><span data-stu-id="b47f2-149">Element</span></span>|<span data-ttu-id="b47f2-150">설명</span><span class="sxs-lookup"><span data-stu-id="b47f2-150">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-netmsmqbinding.md)|<span data-ttu-id="b47f2-151">대기 중인 전송에 대한 전송 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b47f2-151">Defines the transport security settings for queued transports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b47f2-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b47f2-152">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [<span data-ttu-id="b47f2-153">WCF의 큐</span><span class="sxs-lookup"><span data-stu-id="b47f2-153">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="b47f2-154">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="b47f2-154">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="b47f2-155">바인딩하</span><span class="sxs-lookup"><span data-stu-id="b47f2-155">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b47f2-156">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="b47f2-156">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="b47f2-157">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="b47f2-157">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
