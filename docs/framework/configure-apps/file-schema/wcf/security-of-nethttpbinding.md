---
title: <netHttpBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: dc41f6f7-cabc-4a64-9fa0-ceabf861b348
ms.openlocfilehash: 97c52fa4f062ed0c65d5b1a8ca47a1439ab04cf5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736486"
---
# <a name="security-of-nethttpbinding"></a><span data-ttu-id="2c13e-102">\<netHttpBinding>의 \<security></span><span class="sxs-lookup"><span data-stu-id="2c13e-102">\<security> of \<netHttpBinding></span></span>

<span data-ttu-id="2c13e-103">의 보안 기능을 정의 합니다 [\<netHttpBinding>](nethttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="2c13e-103">Defines the security capabilities of the [\<netHttpBinding>](nethttpbinding.md).</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  

## <a name="syntax"></a><span data-ttu-id="2c13e-104">구문</span><span class="sxs-lookup"><span data-stu-id="2c13e-104">Syntax</span></span>

```xml
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2c13e-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2c13e-105">Attributes and elements</span></span>

<span data-ttu-id="2c13e-106">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2c13e-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="2c13e-107">특성</span><span class="sxs-lookup"><span data-stu-id="2c13e-107">Attributes</span></span>

|<span data-ttu-id="2c13e-108">attribute</span><span class="sxs-lookup"><span data-stu-id="2c13e-108">Attribute</span></span>|<span data-ttu-id="2c13e-109">Description</span><span class="sxs-lookup"><span data-stu-id="2c13e-109">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="2c13e-110">mode</span><span class="sxs-lookup"><span data-stu-id="2c13e-110">mode</span></span>|<span data-ttu-id="2c13e-111">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="2c13e-111">Optional.</span></span> <span data-ttu-id="2c13e-112">사용되는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2c13e-112">Specifies the type of security that is used.</span></span> <span data-ttu-id="2c13e-113">기본값은 `None`입니다.</span><span class="sxs-lookup"><span data-stu-id="2c13e-113">The default is `None`.</span></span> <span data-ttu-id="2c13e-114">이 특성은 <xref:System.ServiceModel.BasicHttpSecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2c13e-114">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|

## <a name="mode-attribute"></a><span data-ttu-id="2c13e-115">mode 특성</span><span class="sxs-lookup"><span data-stu-id="2c13e-115">mode attribute</span></span>

|<span data-ttu-id="2c13e-116">값</span><span class="sxs-lookup"><span data-stu-id="2c13e-116">Value</span></span>|<span data-ttu-id="2c13e-117">Description</span><span class="sxs-lookup"><span data-stu-id="2c13e-117">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="2c13e-118">None</span><span class="sxs-lookup"><span data-stu-id="2c13e-118">None</span></span>|<span data-ttu-id="2c13e-119">-전송 중에는 메시지의 보안이 유지 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c13e-119">-   Messages are not secured during transfer.</span></span>|
|<span data-ttu-id="2c13e-120">전송</span><span class="sxs-lookup"><span data-stu-id="2c13e-120">Transport</span></span>|<span data-ttu-id="2c13e-121">HTTPS 전송을 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c13e-121">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="2c13e-122">SOAP 메시지는 HTTPS를 통해 보안이 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c13e-122">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="2c13e-123">이 서비스는 서비스의 X.509 인증서를 사용하여 클라이언트에 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c13e-123">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="2c13e-124">클라이언트는 제공된 ClientCredentialType을 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c13e-124">The client is authenticated using the ClientCredentialType supplied.</span></span>|
|<span data-ttu-id="2c13e-125">메시지</span><span class="sxs-lookup"><span data-stu-id="2c13e-125">Message</span></span>|<span data-ttu-id="2c13e-126">SOAP 메시지 보안을 사용하여 보안이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c13e-126">Security is provided using SOAP message security.</span></span> <span data-ttu-id="2c13e-127">기본적으로 본문에는 암호화 및 서명이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c13e-127">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="2c13e-128">이 바인딩에서는 클라이언트에 out of band 방식으로 서버 인증서가 제공되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c13e-128">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="2c13e-129">이 바인딩의 유효한 `ClientCredentialType`은 `Certificate`뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="2c13e-129">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|
|<span data-ttu-id="2c13e-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="2c13e-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="2c13e-131">전송 보안에 의해 무결성, 기밀성 및 서버 인증이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c13e-131">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="2c13e-132">클라이언트 인증은 SOAP 메시지 보안에 의해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c13e-132">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="2c13e-133">이 모드는 사용자가 사용자 이름/암호를 사용하여 인증되며 메시지 전송 보호를 위한 기존의 HTTP 배포가 있는 경우에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="2c13e-133">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|
|<span data-ttu-id="2c13e-134">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="2c13e-134">TransportCredentialOnly</span></span>|<span data-ttu-id="2c13e-135">이 모드는 메시지 무결성 및 기밀성을 제공하지 않으나</span><span class="sxs-lookup"><span data-stu-id="2c13e-135">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="2c13e-136">http 기반 클라이언트 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2c13e-136">It provides http-based client authentication.</span></span> <span data-ttu-id="2c13e-137">이 모드는 주의해서 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c13e-137">This mode should be used with caution.</span></span> <span data-ttu-id="2c13e-138">다른 방법 (예: IPSec)에서 전송 보안을 제공 하는 환경에서 사용 해야 하며, WCF 인프라에서 클라이언트 인증만 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c13e-138">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="2c13e-139">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2c13e-139">Child elements</span></span>

|<span data-ttu-id="2c13e-140">요소</span><span class="sxs-lookup"><span data-stu-id="2c13e-140">Element</span></span>|<span data-ttu-id="2c13e-141">Description</span><span class="sxs-lookup"><span data-stu-id="2c13e-141">Description</span></span>|
|-------------|-----------------|
|[\<transport>](transport-of-nethttpbinding.md)|<span data-ttu-id="2c13e-142">기본 HTTP 서비스에 대한 전송 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2c13e-142">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="2c13e-143">이 요소는 <xref:System.ServiceModel.HttpTransportSecurity>에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="2c13e-143">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|
|[\<message>](message-of-nethttpbinding.md)|<span data-ttu-id="2c13e-144">기본 HTTP 서비스에 대한 메시지 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2c13e-144">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="2c13e-145">이 요소는 <xref:System.ServiceModel.BasicHttpMessageSecurity>에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="2c13e-145">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="2c13e-146">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2c13e-146">Parent elements</span></span>

|<span data-ttu-id="2c13e-147">요소</span><span class="sxs-lookup"><span data-stu-id="2c13e-147">Element</span></span>|<span data-ttu-id="2c13e-148">Description</span><span class="sxs-lookup"><span data-stu-id="2c13e-148">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="2c13e-149">바인딩</span><span class="sxs-lookup"><span data-stu-id="2c13e-149">binding</span></span>|<span data-ttu-id="2c13e-150">의 바인딩 요소 [\<basicHttpBinding>](basichttpbinding.md) 입니다.</span><span class="sxs-lookup"><span data-stu-id="2c13e-150">The binding element of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|

## <a name="remarks"></a><span data-ttu-id="2c13e-151">설명</span><span class="sxs-lookup"><span data-stu-id="2c13e-151">Remarks</span></span>

 <span data-ttu-id="2c13e-152">기본적으로 SOAP 메시지는 보안이 설정 되지 않으며 클라이언트는 인증 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c13e-152">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="2c13e-153">이 요소를 사용하면 `netHttpBinding` 요소에 대한 추가 보안 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c13e-153">This element enables you to configure additional security settings for the `netHttpBinding` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="2c13e-154">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2c13e-154">See also</span></span>

- <xref:System.ServiceModel.NetHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetHttpBindingElement.Security%2A>  
- [<span data-ttu-id="2c13e-155">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="2c13e-155">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="2c13e-156">자격 증명 형식 선택</span><span class="sxs-lookup"><span data-stu-id="2c13e-156">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="2c13e-157">바인딩</span><span class="sxs-lookup"><span data-stu-id="2c13e-157">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="2c13e-158">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="2c13e-158">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="2c13e-159">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="2c13e-159">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
