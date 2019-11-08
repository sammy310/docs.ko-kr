---
title: <netMsmqBinding>의 <message>
ms.date: 03/30/2017
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
ms.openlocfilehash: 5a4a4e8b645ee2c607988ac3031af537c93ca8c0
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736750"
---
# <a name="message-of-netmsmqbinding"></a><span data-ttu-id="8ae9a-102">\<메시지 > \<netMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="8ae9a-102">\<message> of \<netMsmqBinding></span></span>

<span data-ttu-id="8ae9a-103">이 `netMsmqBinding` 바인딩에 대한 SOAP 메시지 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-103">Defines the SOAP message security settings on this `netMsmqBinding` binding.</span></span>

<span data-ttu-id="8ae9a-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8ae9a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8ae9a-105">[ **\<system serviceModel >** ](system-servicemodel.md) &nbsp; &nbsp; </span><span class="sxs-lookup"><span data-stu-id="8ae9a-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8ae9a-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**바인딩**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="8ae9a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="8ae9a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netMsmqBinding >** ](netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="8ae9a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)</span></span>\
<span data-ttu-id="8ae9a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="8ae9a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="8ae9a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**security >** ](security-of-netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="8ae9a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netmsmqbinding.md)</span></span>\
<span data-ttu-id="8ae9a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**메시지 >**</span><span class="sxs-lookup"><span data-stu-id="8ae9a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="8ae9a-111">구문</span><span class="sxs-lookup"><span data-stu-id="8ae9a-111">Syntax</span></span>

```xml
<netMsmqBinding>
  <binding>
    <security>
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
    </security>
  </binding>
</netMsmqBinding>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8ae9a-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8ae9a-112">Attributes and Elements</span></span>

<span data-ttu-id="8ae9a-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-113">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="8ae9a-114">특성</span><span class="sxs-lookup"><span data-stu-id="8ae9a-114">Attributes</span></span>

|<span data-ttu-id="8ae9a-115">특성</span><span class="sxs-lookup"><span data-stu-id="8ae9a-115">Attribute</span></span>|<span data-ttu-id="8ae9a-116">설명</span><span class="sxs-lookup"><span data-stu-id="8ae9a-116">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="8ae9a-117">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="8ae9a-117">algorithmSuite</span></span>|<span data-ttu-id="8ae9a-118">MSMQ 전송을 통해 전송되는 메시지에 메시지 기반 보안을 적용하는 데 사용되는 메시지 암호화 및 키 랩 알고리즘을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-118">Sets the message encryption and key-wrap algorithms that are used to achieve message-based security for messages sent over MSMQ transport.</span></span><br /><br /> <span data-ttu-id="8ae9a-119">기본값은 `Aes256`여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-119">The default value is `Aes256`.</span></span> <span data-ttu-id="8ae9a-120">이 특성은 <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-120">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span>|
|<span data-ttu-id="8ae9a-121">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="8ae9a-121">clientCredentialType</span></span>|<span data-ttu-id="8ae9a-122">MSMQ 전송을 통해 전송되는 메시지에 대해 클라이언트 인증을 수행할 때 사용되는 자격 증명의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-122">Specifies the type of credential to be used when performing client authentication for messages sent over the MSMQ transport.</span></span> <span data-ttu-id="8ae9a-123">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-123">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="8ae9a-124">-없음: 서비스가 익명 클라이언트와 상호 작용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-124">-   None: This allows the service to interact with anonymous clients.</span></span> <span data-ttu-id="8ae9a-125">서비스와 클라이언트 모두 자격 증명이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-125">Neither the service nor the client requires a credential.</span></span><br /><span data-ttu-id="8ae9a-126">-Windows: Windows 자격 증명의 인증 된 컨텍스트에서 SOAP 교환을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-126">-   Windows: This enables the SOAP exchanges to be under the authenticated context of a Windows credential.</span></span> <span data-ttu-id="8ae9a-127">이는 항상 Kerberos 기반 인증을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-127">This always performs Kerberos-based authentication.</span></span><br /><span data-ttu-id="8ae9a-128">-UserName: 서비스에서 사용자 이름 자격 증명을 사용 하 여 클라이언트를 인증 하도록 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-128">-   UserName: This enables the service to require that the client be authenticated using a UserName credential.</span></span> <span data-ttu-id="8ae9a-129">이 경우에는 `clientCredentials` 동작을 사용 하 여 자격 증명을 지정 해야 합니다 **. 주의:** WINDOWS COMMUNICATION FOUNDATION (WCF)는 암호를 사용 하거나 암호를 사용 하 여 키를 파생 하거나 메시지 보안에 이러한 키를 사용 하는 것을 지원 하지 않습니다</span><span class="sxs-lookup"><span data-stu-id="8ae9a-129">The credential in this case needs to be specified using the `clientCredentials` behavior **Caution:**  Windows Communication Foundation (WCF) does not support sending a password digest or deriving keys using password and using such keys for message security.</span></span> <span data-ttu-id="8ae9a-130">따라서 WCF는 사용자 이름 자격 증명을 사용할 때 exchange가 보호 되도록 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-130">Therefore, WCF enforces that the exchange is secured when using UserName credentials.</span></span> <span data-ttu-id="8ae9a-131">이 모드에서는 `clientCredential` 동작 및 `serviceCertificate`를 사용하여 클라이언트에 서비스 인증서를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-131">This mode requires that the service certificate be specified on the client side using `clientCredential` behavior and `serviceCertificate`.</span></span> <br /><br /> <span data-ttu-id="8ae9a-132">-Certificate: 서비스에서 인증서를 사용 하 여 클라이언트를 인증 하도록 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-132">-   Certificate: This enables the service to require that the client be authenticated using a certificate.</span></span> <span data-ttu-id="8ae9a-133">이 경우 `clientCredentials` 동작을 사용하여 클라이언트 자격 증명을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-133">The client credential in this case needs to be specified using the `clientCredentials` behavior.</span></span> <span data-ttu-id="8ae9a-134">이 경우 `clientCredentials`를 지정하여 `serviceCertificate` 동작을 통해 서비스 자격 증명을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-134">The service credential in this case needs to be specified using the `clientCredentials` behavior by specifying the `serviceCertificate`.</span></span><br /><span data-ttu-id="8ae9a-135">-CardSpace: 서비스에서 CardSpace를 사용 하 여 클라이언트를 인증 하도록 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-135">-   CardSpace: This allows the service to require that the client be authenticated using a CardSpace.</span></span> <span data-ttu-id="8ae9a-136">`serviceCertificate` `clientCredential` 동작으로 프로 비전 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-136">The `serviceCertificate` must be provisioned in the `clientCredential` behavior.</span></span><br /><br /> <span data-ttu-id="8ae9a-137">기본값은 `Windows`여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-137">The default value is `Windows`.</span></span> <span data-ttu-id="8ae9a-138">이 특성은 <xref:System.ServiceModel.MessageCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-138">This attribute is of type <xref:System.ServiceModel.MessageCredentialType>.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="8ae9a-139">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8ae9a-139">Child Elements</span></span>

<span data-ttu-id="8ae9a-140">없음</span><span class="sxs-lookup"><span data-stu-id="8ae9a-140">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8ae9a-141">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8ae9a-141">Parent Elements</span></span>

|<span data-ttu-id="8ae9a-142">요소</span><span class="sxs-lookup"><span data-stu-id="8ae9a-142">Element</span></span>|<span data-ttu-id="8ae9a-143">설명</span><span class="sxs-lookup"><span data-stu-id="8ae9a-143">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8ae9a-144">\<security ></span><span class="sxs-lookup"><span data-stu-id="8ae9a-144">\<security></span></span>](security-of-netmsmqbinding.md)|<span data-ttu-id="8ae9a-145">바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-145">Defines the security settings for a binding.</span></span>|

## <a name="see-also"></a><span data-ttu-id="8ae9a-146">참조</span><span class="sxs-lookup"><span data-stu-id="8ae9a-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>
- <xref:System.ServiceModel.MessageSecurityOverMsmq>
- [<span data-ttu-id="8ae9a-147">WCF의 큐</span><span class="sxs-lookup"><span data-stu-id="8ae9a-147">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="8ae9a-148">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="8ae9a-148">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="8ae9a-149">바인딩</span><span class="sxs-lookup"><span data-stu-id="8ae9a-149">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="8ae9a-150">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="8ae9a-150">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="8ae9a-151">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="8ae9a-151">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="8ae9a-152">\<binding ></span><span class="sxs-lookup"><span data-stu-id="8ae9a-152">\<binding></span></span>](bindings.md)
