---
description: 다음에 대해 자세히 알아보세요. <msmqTransportSecurity>
title: <msmqTransportSecurity>
ms.date: 03/30/2017
ms.assetid: 092e911b-ab1b-4069-a26e-6134c3299e06
ms.openlocfilehash: d5a681c287749598c8c80470ea6d800f1687a80d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99684167"
---
# \<msmqTransportSecurity>

<span data-ttu-id="5fe10-102">사용자 지정 바인딩에 MSMQ 전송 보안 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5fe10-102">Specifies MSMQ transport security settings for a custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqIntegration>**](msmqintegration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<msmqTransportSecurity>**  
  
## <a name="syntax"></a><span data-ttu-id="5fe10-103">구문</span><span class="sxs-lookup"><span data-stu-id="5fe10-103">Syntax</span></span>  
  
```xml  
<msmqTransportSecurity msmqAuthenticationMode="None/Windows/Certificate"
                       msmqEncryptionAlgorithm="RC4Stream/AES"
                       msmqProtectionLevel="None/Sign/EncryptAndSign"
                       msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
</msmqTransportSecurity>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5fe10-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5fe10-104">Attributes and Elements</span></span>  

 <span data-ttu-id="5fe10-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5fe10-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5fe10-106">특성</span><span class="sxs-lookup"><span data-stu-id="5fe10-106">Attributes</span></span>  
  
|<span data-ttu-id="5fe10-107">attribute</span><span class="sxs-lookup"><span data-stu-id="5fe10-107">Attribute</span></span>|<span data-ttu-id="5fe10-108">설명</span><span class="sxs-lookup"><span data-stu-id="5fe10-108">Description</span></span>|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|<span data-ttu-id="5fe10-109">메시지가 MSMQ 전송에 의해 인증되는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5fe10-109">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="5fe10-110">이 특성이 `None`으로 설정되면 `msmqProtectionLevel` 특성 값도 `None`으로 설정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fe10-110">If this is set to `None`, the value of the `msmqProtectionLevel` attribute must also be set to `None`.</span></span><br /><br /> <span data-ttu-id="5fe10-111">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5fe10-111">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="5fe10-112">-없음: 인증 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5fe10-112">-   None: No authentication.</span></span><br /><span data-ttu-id="5fe10-113">-Windows: 인증 메커니즘은 Active Directory를 사용 하 여 메시지와 연결 된 SID에 대 한 x.509 인증서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5fe10-113">-   Windows: The authentication mechanism uses Active Directory to get the X.509 certificate for the SID associated with the message.</span></span> <span data-ttu-id="5fe10-114">그런 다음 이 인증서는 사용자에게 큐에 대한 쓰기 권한이 있는지 확인하기 위해 큐의 ACL을 검사하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fe10-114">This is then used to check the ACL of the queue to ensure the user has permission to write to the queue.</span></span><br /><span data-ttu-id="5fe10-115">-Certificate: 채널은 인증서 저장소에서 인증서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5fe10-115">-   Certificate: The channel gets the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="5fe10-116">기본값은 Windows입니다.</span><span class="sxs-lookup"><span data-stu-id="5fe10-116">The default value is Windows.</span></span> <span data-ttu-id="5fe10-117">이 특성은 <xref:System.ServiceModel.MsmqAuthenticationMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5fe10-117">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode>.</span></span>|  
|`msmqEncryptionAlgorithm`|<span data-ttu-id="5fe10-118">메시지 큐 관리자 간에 메시지를 전송할 때 통신 중에 메시지 암호화에 사용할 알고리즘을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5fe10-118">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="5fe10-119">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5fe10-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="5fe10-120">-RC4Stream</span><span class="sxs-lookup"><span data-stu-id="5fe10-120">-   RC4Stream</span></span><br /><span data-ttu-id="5fe10-121">-AES</span><span class="sxs-lookup"><span data-stu-id="5fe10-121">-   AES</span></span><br /><br /> <span data-ttu-id="5fe10-122">기본값은 RC4Stream입니다.</span><span class="sxs-lookup"><span data-stu-id="5fe10-122">The default value is RC4Stream.</span></span> <span data-ttu-id="5fe10-123">이 특성은 <xref:System.ServiceModel.MsmqEncryptionAlgorithm> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5fe10-123">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|`msmqProtectionLevel`|<span data-ttu-id="5fe10-124">메시지가 MSMQ 전송 수준에서 보호되는 방식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5fe10-124">Specifies how the message is secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="5fe10-125">암호화는 메시지 무결성을 보장 하는 반면 EncryptAndSign는 메시지 무결성 및 부인 방지를 모두 보장 합니다. 즉, 메시지는 보낸 사람 으로부터 전송 되 고 보낸 사람은 보낸 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="5fe10-125">Encryption ensures message integrity while EncryptAndSign ensures both message integrity and non-repudiation; that is, the message indeed comes from the sender and the sender is who they say they are.</span></span> <span data-ttu-id="5fe10-126">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5fe10-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="5fe10-127">-없음: 보호 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5fe10-127">-   None: No protection.</span></span><br /><span data-ttu-id="5fe10-128">-서명: 메시지가 서명 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fe10-128">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="5fe10-129">-EncryptAndSign: 메시지가 암호화 되 고 서명 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fe10-129">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="5fe10-130">기본값은 Sign입니다.</span><span class="sxs-lookup"><span data-stu-id="5fe10-130">The default value is Sign.</span></span> <span data-ttu-id="5fe10-131">이 특성은 <xref:System.Net.Security.ProtectionLevel> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5fe10-131">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
|`msmqSecureHashAlgorithm`|<span data-ttu-id="5fe10-132">시그니처의 일부로 다이제스트를 계산하는 데 사용되는 알고리즘을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5fe10-132">Specifies the algorithm to be used in computing the digest as part of signatures.</span></span> <span data-ttu-id="5fe10-133">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5fe10-133">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="5fe10-134">-MD5</span><span class="sxs-lookup"><span data-stu-id="5fe10-134">-   MD5</span></span><br /><span data-ttu-id="5fe10-135">-SHA1</span><span class="sxs-lookup"><span data-stu-id="5fe10-135">-   SHA1</span></span><br /><span data-ttu-id="5fe10-136">-SHA256</span><span class="sxs-lookup"><span data-stu-id="5fe10-136">-   SHA256</span></span><br /><span data-ttu-id="5fe10-137">-SHA512</span><span class="sxs-lookup"><span data-stu-id="5fe10-137">-   SHA512</span></span><br /><br /> <span data-ttu-id="5fe10-138">기본값은 SHA1입니다.</span><span class="sxs-lookup"><span data-stu-id="5fe10-138">The default value is SHA1.</span></span> <span data-ttu-id="5fe10-139">이 특성은 <xref:System.ServiceModel.MsmqSecureHashAlgorithm> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5fe10-139">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span><br><span data-ttu-id="5fe10-140">MD5 및 s h a 1의 충돌 문제로 인해 s h a 1 이상을 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fe10-140">Due to collision problems with MD5 and SHA1, Microsoft recommends SHA256 or better.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5fe10-141">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5fe10-141">Child Elements</span></span>  

 <span data-ttu-id="5fe10-142">없음</span><span class="sxs-lookup"><span data-stu-id="5fe10-142">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5fe10-143">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5fe10-143">Parent Elements</span></span>  
  
|<span data-ttu-id="5fe10-144">요소</span><span class="sxs-lookup"><span data-stu-id="5fe10-144">Element</span></span>|<span data-ttu-id="5fe10-145">설명</span><span class="sxs-lookup"><span data-stu-id="5fe10-145">Description</span></span>|  
|-------------|-----------------|  
|[\<msmqIntegration>](msmqintegration.md)|<span data-ttu-id="5fe10-146">MSMQ(메시지 큐) 전송자 또는 수신자와의 상호 작용에 필요한 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5fe10-146">Specifies settings required for interaction with a Message Queuing (MSMQ) sender or receiver.</span></span>|  
|[\<msmqTransport>](msmqtransport.md)|<span data-ttu-id="5fe10-147">네이티브 MSMQ 프로토콜을 사용하는 WCF(Windows Communication Foundation) 서비스에 대한 큐 통신 속성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5fe10-147">Specifies the queuing communication properties for a Windows Communication Foundation (WCF) service that uses the native MSMQ protocol.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5fe10-148">설명</span><span class="sxs-lookup"><span data-stu-id="5fe10-148">Remarks</span></span>  

 <span data-ttu-id="5fe10-149">전송 보안에 대 한 자세한 내용은 [전송 보안](../../../wcf/feature-details/transport-security.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5fe10-149">For more information on transport security, see [Transport Security](../../../wcf/feature-details/transport-security.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fe10-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5fe10-150">See also</span></span>

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="5fe10-151">WCF의 큐</span><span class="sxs-lookup"><span data-stu-id="5fe10-151">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="5fe10-152">전송</span><span class="sxs-lookup"><span data-stu-id="5fe10-152">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="5fe10-153">전송 선택</span><span class="sxs-lookup"><span data-stu-id="5fe10-153">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="5fe10-154">바인딩</span><span class="sxs-lookup"><span data-stu-id="5fe10-154">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5fe10-155">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="5fe10-155">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="5fe10-156">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="5fe10-156">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="5fe10-157">전송 보안</span><span class="sxs-lookup"><span data-stu-id="5fe10-157">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
