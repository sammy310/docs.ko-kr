---
title: <netTcpBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: 286cd191-4fd5-4c4e-a223-9c71cf7fdead
ms.openlocfilehash: d39e3e5e655817aa91c5301274a860a00a6ab7ef
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169988"
---
# <a name="security-of-nettcpbinding"></a><span data-ttu-id="5cef0-102">\<netTcpBinding>의 \<security></span><span class="sxs-lookup"><span data-stu-id="5cef0-102">\<security> of \<netTcpBinding></span></span>

<span data-ttu-id="5cef0-103">바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5cef0-103">Defines the security settings for a binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netTcpBinding>**](nettcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="5cef0-104">구문</span><span class="sxs-lookup"><span data-stu-id="5cef0-104">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             protectionLevel="None/Sign/EncryptAndSign" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5cef0-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5cef0-105">Attributes and Elements</span></span>  

 <span data-ttu-id="5cef0-106">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5cef0-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5cef0-107">특성</span><span class="sxs-lookup"><span data-stu-id="5cef0-107">Attributes</span></span>  
  
|<span data-ttu-id="5cef0-108">attribute</span><span class="sxs-lookup"><span data-stu-id="5cef0-108">Attribute</span></span>|<span data-ttu-id="5cef0-109">설명</span><span class="sxs-lookup"><span data-stu-id="5cef0-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5cef0-110">mode</span><span class="sxs-lookup"><span data-stu-id="5cef0-110">mode</span></span>|<span data-ttu-id="5cef0-111">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="5cef0-111">Optional.</span></span> <span data-ttu-id="5cef0-112">적용되는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5cef0-112">Specifies the type of security that is applied.</span></span> <span data-ttu-id="5cef0-113">유효한 값이 아래에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cef0-113">Valid values are shown below.</span></span> <span data-ttu-id="5cef0-114">기본값은 `Transport`입니다.</span><span class="sxs-lookup"><span data-stu-id="5cef0-114">The default value is `Transport`.</span></span><br /><br /> <span data-ttu-id="5cef0-115">이 특성은 <xref:System.ServiceModel.SecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5cef0-115">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="5cef0-116">mode 특성</span><span class="sxs-lookup"><span data-stu-id="5cef0-116">mode Attribute</span></span>  
  
|<span data-ttu-id="5cef0-117">Value</span><span class="sxs-lookup"><span data-stu-id="5cef0-117">Value</span></span>|<span data-ttu-id="5cef0-118">설명</span><span class="sxs-lookup"><span data-stu-id="5cef0-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5cef0-119">없음</span><span class="sxs-lookup"><span data-stu-id="5cef0-119">None</span></span>|<span data-ttu-id="5cef0-120">보안이 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cef0-120">Security is disabled.</span></span>|  
|<span data-ttu-id="5cef0-121">전송</span><span class="sxs-lookup"><span data-stu-id="5cef0-121">Transport</span></span>|<span data-ttu-id="5cef0-122">전송 보안은 TCP를 통한 TLS 또는 SPNego를 사용하여 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cef0-122">Transport security is provided using TLS over TCP or SPNego.</span></span> <span data-ttu-id="5cef0-123">서비스는 SSL 인증서로 구성해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cef0-123">The service may need to be configured with SSL certificates.</span></span> <span data-ttu-id="5cef0-124">이 모드에서는 보호 수준을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cef0-124">It is possible to control the protection level with this mode.</span></span>|  
|<span data-ttu-id="5cef0-125">메시지</span><span class="sxs-lookup"><span data-stu-id="5cef0-125">Message</span></span>|<span data-ttu-id="5cef0-126">SOAP 메시지 보안을 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cef0-126">Security is provided using SOAP message security.</span></span> <span data-ttu-id="5cef0-127">기본적으로 SOAP 본문은 암호화되고 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cef0-127">By default, the SOAP body is encrypted and signed.</span></span> <span data-ttu-id="5cef0-128">이 모드는 서비스 자격 증명을 클라이언트에서 밴드 외 방식으로 사용할 수 있는지 여부, 사용할 알고리즘 모음, 메시지 본문에 적용될 보호 수준과 같은 다양한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5cef0-128">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body.</span></span> <span data-ttu-id="5cef0-129">클라이언트 인증은 세션당 한 번씩 수행되며 세션 기간 동안 인증 결과가 캐시에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cef0-129">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="5cef0-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="5cef0-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="5cef0-131">전송 보안이 메시지 보안과 결합되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cef0-131">Transport security is coupled with message security.</span></span> <span data-ttu-id="5cef0-132">전송 보안은 TCP를 통한 TLS 또는 SPNego를 사용하여 제공되며 무결성, 기밀성 및 서버 인증을 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="5cef0-132">Transport security is provided by TLS over TCP, or SPNego, and ensures integrity, confidentiality, and server authentication.</span></span> <span data-ttu-id="5cef0-133">SOAP 메시지 보안에서는 클라이언트 인증이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cef0-133">SOAP message security provides client authentication.</span></span> <span data-ttu-id="5cef0-134">기본적으로 클라이언트 인증은 세션당 한 번씩 수행되며 세션 기간 동안 인증 결과가 캐시에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cef0-134">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5cef0-135">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5cef0-135">Child Elements</span></span>  
  
|<span data-ttu-id="5cef0-136">요소</span><span class="sxs-lookup"><span data-stu-id="5cef0-136">Element</span></span>|<span data-ttu-id="5cef0-137">설명</span><span class="sxs-lookup"><span data-stu-id="5cef0-137">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-nettcpbinding.md)|<span data-ttu-id="5cef0-138">전송의 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5cef0-138">Defines the security settings for the transport.</span></span> <span data-ttu-id="5cef0-139">이 요소는 <xref:System.ServiceModel.Configuration.TcpTransportSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5cef0-139">This element is of type <xref:System.ServiceModel.Configuration.TcpTransportSecurityElement>.</span></span>|  
|[\<message>](message-element-of-nettcpbinding.md)|<span data-ttu-id="5cef0-140">메시지에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5cef0-140">Defines the security settings for the message.</span></span> <span data-ttu-id="5cef0-141">이 요소는 <xref:System.ServiceModel.Configuration.MessageSecurityOverTcpElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5cef0-141">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverTcpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5cef0-142">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5cef0-142">Parent Elements</span></span>  
  
|<span data-ttu-id="5cef0-143">요소</span><span class="sxs-lookup"><span data-stu-id="5cef0-143">Element</span></span>|<span data-ttu-id="5cef0-144">설명</span><span class="sxs-lookup"><span data-stu-id="5cef0-144">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5cef0-145">바인딩</span><span class="sxs-lookup"><span data-stu-id="5cef0-145">binding</span></span>|<span data-ttu-id="5cef0-146">의 바인딩 요소 [\<netTcpBinding>](nettcpbinding.md) 입니다.</span><span class="sxs-lookup"><span data-stu-id="5cef0-146">The binding element of the [\<netTcpBinding>](nettcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5cef0-147">설명</span><span class="sxs-lookup"><span data-stu-id="5cef0-147">Remarks</span></span>  

 <span data-ttu-id="5cef0-148">각 표준 바인딩은 전송 보안 요구 사항을 제어 하기 위한 매개 변수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cef0-148">Each of the standard bindings provides parameters for controlling the transfer security requirements.</span></span> <span data-ttu-id="5cef0-149">이러한 매개 변수에는 일반적으로 메시지 수준 또는 전송 수준 보안이 사용 되는지 여부와 선택 된 클라이언트 자격 증명 형식을 지정 하는 보안 모드가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cef0-149">These parameters typically include the security mode that specified whether message-level or transport-level security is used and the choice of client credential type.</span></span> <span data-ttu-id="5cef0-150">이러한 매개 변수가 제공 하는 옵션에 따라 적절 한 보안을 사용 하 여 채널 스택이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cef0-150">Based on the choice of options these parameters present, a channel stack is constructed with appropriate security.</span></span>  
  
 <span data-ttu-id="5cef0-151">WCF (Windows Communication Foundation)에서 제공 하는 시스템 제공 바인딩은 가장 일반적인 시나리오 요구 사항 중 일부를 충족 하도록 설계 된 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="5cef0-151">The system-provided bindings supplied by Windows Communication Foundation (WCF) are a set designed to meet some of the most common scenario requirements.</span></span> <span data-ttu-id="5cef0-152">이러한 각 바인딩은 특정 대상 시나리오에 대 한 보안 요구 사항을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cef0-152">Each of these bindings allows the specification of security requirements for some specific targeted scenarios.</span></span>  
  
 <span data-ttu-id="5cef0-153">이 구성 요소는 `netTcpBinding`의 보안 사양을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5cef0-153">This configuration element provides the security specifications for `netTcpBinding`.</span></span> <span data-ttu-id="5cef0-154">이는 시스템 간 통신에 적합 한 안전 하 고 신뢰할 수 있으며 최적화 된 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="5cef0-154">This is a secure, reliable, optimized binding suitable for cross-machine communication.</span></span> <span data-ttu-id="5cef0-155">기본적으로 메시지 배달을 위한 TCP, 메시지 보안 및 인증을 위한 Windows 보안, 안정성을 위한 WS-Reliable Messaging 및 이진 메시지 인코딩을 지원하는 런타임 통신 스택을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="5cef0-155">By default it generates a runtime communication stack supporting TCP for message delivery and Windows Security for message security and authentication, WS-ReliableMessaging for reliability, and binary message encoding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cef0-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5cef0-156">See also</span></span>

- <xref:System.ServiceModel.NetTcpSecurity>
- <xref:System.ServiceModel.NetTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [<span data-ttu-id="5cef0-157">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="5cef0-157">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="5cef0-158">바인딩하</span><span class="sxs-lookup"><span data-stu-id="5cef0-158">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5cef0-159">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="5cef0-159">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="5cef0-160">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="5cef0-160">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
