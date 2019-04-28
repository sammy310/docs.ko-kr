---
title: <netMsmqBinding>의 <message>
ms.date: 03/30/2017
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
ms.openlocfilehash: c623b7daf1e91c9c1800b9653525cd51b1087506
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768955"
---
# <a name="message-of-netmsmqbinding"></a><span data-ttu-id="14725-102">\<message> of \<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="14725-102">\<message> of \<netMsmqBinding></span></span>

<span data-ttu-id="14725-103">이 `netMsmqBinding` 바인딩에 대한 SOAP 메시지 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="14725-103">Defines the SOAP message security settings on this `netMsmqBinding` binding.</span></span>

```xml
<system.ServiceModel>
  <bindings>
    <netMsmqBinding>
      <binding>
        <security>
          <message>
```

## <a name="syntax"></a><span data-ttu-id="14725-104">구문</span><span class="sxs-lookup"><span data-stu-id="14725-104">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="14725-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="14725-105">Attributes and Elements</span></span>

<span data-ttu-id="14725-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="14725-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="14725-107">특성</span><span class="sxs-lookup"><span data-stu-id="14725-107">Attributes</span></span>

|<span data-ttu-id="14725-108">특성</span><span class="sxs-lookup"><span data-stu-id="14725-108">Attribute</span></span>|<span data-ttu-id="14725-109">설명</span><span class="sxs-lookup"><span data-stu-id="14725-109">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="14725-110">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="14725-110">algorithmSuite</span></span>|<span data-ttu-id="14725-111">MSMQ 전송을 통해 전송되는 메시지에 메시지 기반 보안을 적용하는 데 사용되는 메시지 암호화 및 키 랩 알고리즘을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="14725-111">Sets the message encryption and key-wrap algorithms that are used to achieve message-based security for messages sent over MSMQ transport.</span></span><br /><br /> <span data-ttu-id="14725-112">기본값은 `Aes256`입니다.</span><span class="sxs-lookup"><span data-stu-id="14725-112">The default value is `Aes256`.</span></span> <span data-ttu-id="14725-113">이 특성은 <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="14725-113">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span>|
|<span data-ttu-id="14725-114">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="14725-114">clientCredentialType</span></span>|<span data-ttu-id="14725-115">MSMQ 전송을 통해 전송되는 메시지에 대해 클라이언트 인증을 수행할 때 사용되는 자격 증명의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="14725-115">Specifies the type of credential to be used when performing client authentication for messages sent over the MSMQ transport.</span></span> <span data-ttu-id="14725-116">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="14725-116">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="14725-117">-None. 이를 통해 서비스와 익명 클라이언트가 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14725-117">-   None: This allows the service to interact with anonymous clients.</span></span> <span data-ttu-id="14725-118">서비스와 클라이언트 모두 자격 증명이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14725-118">Neither the service nor the client requires a credential.</span></span><br /><span data-ttu-id="14725-119">-   Windows: 이 통해 Windows 자격 증명의 인증 된 컨텍스트에서 SOAP 교환이 이루어지도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="14725-119">-   Windows: This enables the SOAP exchanges to be under the authenticated context of a Windows credential.</span></span> <span data-ttu-id="14725-120">이 설정은 항상 Kerberos 기반 인증을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="14725-120">This always performs Kerberos-based authentication.</span></span><br /><span data-ttu-id="14725-121">-   UserName: 이 필요 하도록 서비스를 통해 클라이언트가 UserName 자격 증명을 사용 하 여 인증할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14725-121">-   UserName: This enables the service to require that the client be authenticated using a UserName credential.</span></span> <span data-ttu-id="14725-122">자격 증명을 사용 하 여 지정 해야이 경우에 `clientCredentials` 동작 **주의 해야 합니다.**  Windows Communication Foundation (WCF)는 암호 다이제스트를 보내거나 암호를 사용 하 고 메시지 보안에 이러한 키를 사용 하 여 키를 파생를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14725-122">The credential in this case needs to be specified using the `clientCredentials` behavior **Caution:**  Windows Communication Foundation (WCF) does not support sending a password digest or deriving keys using password and using such keys for message security.</span></span> <span data-ttu-id="14725-123">따라서 WCF 사용자 이름 자격 증명을 사용 하는 경우 교환에 보안을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="14725-123">Therefore, WCF enforces that the exchange is secured when using UserName credentials.</span></span> <span data-ttu-id="14725-124">이 모드에서는 `clientCredential` 동작 및 `serviceCertificate`를 사용하여 클라이언트에 서비스 인증서를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14725-124">This mode requires that the service certificate be specified on the client side using `clientCredential` behavior and `serviceCertificate`.</span></span> <br /><br /> <span data-ttu-id="14725-125">-인증서: 이 필요 하도록 서비스를 통해 인증서를 사용 하 여 클라이언트 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="14725-125">-   Certificate: This enables the service to require that the client be authenticated using a certificate.</span></span> <span data-ttu-id="14725-126">이 경우 `clientCredentials` 동작을 사용하여 클라이언트 자격 증명을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14725-126">The client credential in this case needs to be specified using the `clientCredentials` behavior.</span></span> <span data-ttu-id="14725-127">이 경우 `clientCredentials`를 지정하여 `serviceCertificate` 동작을 통해 서비스 자격 증명을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14725-127">The service credential in this case needs to be specified using the `clientCredentials` behavior by specifying the `serviceCertificate`.</span></span><br /><span data-ttu-id="14725-128">-CardSpace 합니다. 필요 하도록 서비스를 사용 하면이 클라이언트는 CardSpace를 사용 하 여 인증할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14725-128">-   CardSpace: This allows the service to require that the client be authenticated using a CardSpace.</span></span> <span data-ttu-id="14725-129">`serviceCertificate` 동작에 `clientCredential`가 제공되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14725-129">The `serviceCertificate` must be provisioned in the `clientCredential` behavior.</span></span><br /><br /> <span data-ttu-id="14725-130">기본값은 `Windows`입니다.</span><span class="sxs-lookup"><span data-stu-id="14725-130">The default value is `Windows`.</span></span> <span data-ttu-id="14725-131">이 특성은 <xref:System.ServiceModel.MessageCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="14725-131">This attribute is of type <xref:System.ServiceModel.MessageCredentialType>.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="14725-132">자식 요소</span><span class="sxs-lookup"><span data-stu-id="14725-132">Child Elements</span></span>

<span data-ttu-id="14725-133">없음</span><span class="sxs-lookup"><span data-stu-id="14725-133">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="14725-134">부모 요소</span><span class="sxs-lookup"><span data-stu-id="14725-134">Parent Elements</span></span>

|<span data-ttu-id="14725-135">요소</span><span class="sxs-lookup"><span data-stu-id="14725-135">Element</span></span>|<span data-ttu-id="14725-136">설명</span><span class="sxs-lookup"><span data-stu-id="14725-136">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="14725-137">\<security></span><span class="sxs-lookup"><span data-stu-id="14725-137">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|<span data-ttu-id="14725-138">바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="14725-138">Defines the security settings for a binding.</span></span>|

## <a name="see-also"></a><span data-ttu-id="14725-139">참고자료</span><span class="sxs-lookup"><span data-stu-id="14725-139">See also</span></span>

- <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>
- <xref:System.ServiceModel.MessageSecurityOverMsmq>
- [<span data-ttu-id="14725-140">WCF의 큐</span><span class="sxs-lookup"><span data-stu-id="14725-140">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="14725-141">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="14725-141">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="14725-142">바인딩</span><span class="sxs-lookup"><span data-stu-id="14725-142">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="14725-143">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="14725-143">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="14725-144">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="14725-144">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="14725-145">\<binding></span><span class="sxs-lookup"><span data-stu-id="14725-145">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
