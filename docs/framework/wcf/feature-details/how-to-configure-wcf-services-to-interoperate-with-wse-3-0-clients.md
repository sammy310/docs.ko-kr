---
description: '자세한 정보: 방법: WSE 3.0 클라이언트와 상호 운용 하도록 WCF 서비스 구성'
title: '방법: WSE 3.0 클라이언트와 상호 운용하도록 WCF 서비스 구성'
ms.date: 03/30/2017
ms.assetid: 0f38c4a0-49a6-437c-bdde-ad1d138d3c4a
ms.openlocfilehash: d48b24ac7787a9863744ee9b6a4a984cb6b371e4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99779935"
---
# <a name="how-to-configure-wcf-services-to-interoperate-with-wse-30-clients"></a><span data-ttu-id="da2cb-103">방법: WSE 3.0 클라이언트와 상호 운용하도록 WCF 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="da2cb-103">How to: Configure WCF Services to Interoperate with WSE 3.0 Clients</span></span>

<span data-ttu-id="da2cb-104">Wcf (Windows Communication Foundation) 서비스는 WS-Addressing 사양의 8 월 2004 버전을 사용 하도록 WCF 서비스를 구성 하는 경우 WSE (Web Services 3.0 향상 된 Microsoft .NET) 클라이언트와 유선 수준으로 호환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da2cb-104">Windows Communication Foundation (WCF) services are wire-level compatible with Web Services Enhancements 3.0 for Microsoft .NET (WSE) clients when WCF services are configured to use the August 2004 version of the WS-Addressing specification.</span></span>

### <a name="to-enable-a-wcf-service-to-interoperate-with-wse-30-clients"></a><span data-ttu-id="da2cb-105">WCF 서비스가 WSE 3.0 클라이언트와 상호 운용하도록 하려면</span><span class="sxs-lookup"><span data-stu-id="da2cb-105">To enable a WCF service to interoperate with WSE 3.0 clients</span></span>

1. <span data-ttu-id="da2cb-106">WCF 서비스에 대 한 사용자 지정 바인딩을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="da2cb-106">Define a custom binding for the WCF service.</span></span>

    <span data-ttu-id="da2cb-107">2004년 8월 버전의 WS-Addressing 사양을 메시지 인코딩에 사용하도록 지정하려면 사용자 지정 바인딩을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da2cb-107">To specify that the August 2004 version of the WS-Addressing specification is used for message encoding, a custom binding must be created.</span></span>

    1. <span data-ttu-id="da2cb-108">[\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) 서비스 구성 파일의에 자식을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="da2cb-108">Add a child [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) to the [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) of the service's configuration file.</span></span>

    2. <span data-ttu-id="da2cb-109">에를 추가 하 고 특성을 설정 하 여 바인딩의 이름을 지정 [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) `name` 합니다.</span><span class="sxs-lookup"><span data-stu-id="da2cb-109">Specify a name for the binding, by adding a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) to the [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) and setting the `name` attribute.</span></span>

    3. <span data-ttu-id="da2cb-110">에 자식을 추가 하 여 WSE 3.0와 호환 되는 메시지를 보호 하는 데 사용 되는 WS-Security 사양의 버전과 인증 모드를 지정 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="da2cb-110">Specify an authentication mode and the version of the WS-Security specifications that are used to secure messages that are compatible with WSE 3.0, by adding a child [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) to the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md).</span></span>

        <span data-ttu-id="da2cb-111">인증 모드를 설정 하려면의 특성을 설정 합니다 `authenticationMode` [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) .</span><span class="sxs-lookup"><span data-stu-id="da2cb-111">To set the authentication mode, set the `authenticationMode` attribute of the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span> <span data-ttu-id="da2cb-112">인증 모드는 대체로 WSE 3.0의 턴키 보안 어설션에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="da2cb-112">An authentication mode is roughly equivalent to a turnkey security assertion in WSE 3.0.</span></span> <span data-ttu-id="da2cb-113">다음 표에서는 WCF의 인증 모드를 WSE 3.0의 턴키 보안 어설션에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="da2cb-113">The following table maps authentication modes in WCF to turnkey security assertions in WSE 3.0.</span></span>

        |<span data-ttu-id="da2cb-114">WCF 인증 모드</span><span class="sxs-lookup"><span data-stu-id="da2cb-114">WCF Authentication Mode</span></span>|<span data-ttu-id="da2cb-115">WSE 3.0 턴키 보안 어설션</span><span class="sxs-lookup"><span data-stu-id="da2cb-115">WSE 3.0 turnkey security assertion</span></span>|
        |-----------------------------|----------------------------------------|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>|`anonymousForCertificateSecurity`|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.Kerberos>|`kerberosSecurity`|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate10Security`*|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate11Security`*|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameOverTransport>|`usernameOverTransportSecurity`|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameForCertificate>|`usernameForCertificateSecurity`|

        <span data-ttu-id="da2cb-116">\* 및 턴키 보안 어설션 간의 주요 차이점 중 하나는 `mutualCertificate10Security` `mutualCertificate11Security` WSE에서 SOAP 메시지 보안을 유지 하는 데 사용 하는 WS-Security 사양의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="da2cb-116">\* One of the primary differences between the `mutualCertificate10Security` and `mutualCertificate11Security` turnkey security assertions is the version of the WS-Security specification that WSE uses to secure the SOAP messages.</span></span> <span data-ttu-id="da2cb-117">`mutualCertificate10Security`에는 WS-Security 1.0이 사용되는 반면, `mutualCertificate11Security`에는 WS-Security 1.1이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="da2cb-117">For `mutualCertificate10Security`, WS-Security 1.0 is used, whereas WS-Security 1.1 is used for `mutualCertificate11Security`.</span></span> <span data-ttu-id="da2cb-118">WCF의 경우의 특성에 WS-Security 사양 버전이 지정 되어 `messageSecurityVersion` [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da2cb-118">For WCF, the version of the WS-Security specification is specified in the `messageSecurityVersion` attribute of the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span>

        <span data-ttu-id="da2cb-119">SOAP 메시지를 보호 하는 데 사용 되는 WS-Security 사양의 버전을 설정 하려면 `messageSecurityVersion` 의 특성을 설정 합니다 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) .</span><span class="sxs-lookup"><span data-stu-id="da2cb-119">To set the version of the WS-Security specification that is used to secure SOAP messages, set the `messageSecurityVersion` attribute of the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span> <span data-ttu-id="da2cb-120">WSE 3.0과 상호 운용하려면 `messageSecurityVersion` 특성의 값을 <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A>으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="da2cb-120">To interoperate with WSE 3.0, set the value of the `messageSecurityVersion` attribute to <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A>.</span></span>

    4. <span data-ttu-id="da2cb-121">를 추가 하 [\<textMessageEncoding>](../../configure-apps/file-schema/wcf/textmessageencoding.md) 고를 해당 값으로 설정 하 여 WCF에서 WS-Addressing 사양의 8 월 2004 버전을 사용 하도록 지정 `messageVersion` <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A> 합니다.</span><span class="sxs-lookup"><span data-stu-id="da2cb-121">Specify that the August 2004 version of the WS-Addressing specification is used by WCF by adding a [\<textMessageEncoding>](../../configure-apps/file-schema/wcf/textmessageencoding.md) and set the `messageVersion` to its value to <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A>.</span></span>

        > [!NOTE]
        > <span data-ttu-id="da2cb-122">SOAP 1.2를 사용할 경우에는 `messageVersion` 특성을 <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A>로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="da2cb-122">When you are using SOAP 1.2, set the `messageVersion` attribute to <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A>.</span></span>

2. <span data-ttu-id="da2cb-123">서비스에서 사용자 지정 바인딩이 사용되도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="da2cb-123">Specify that the service uses the custom binding.</span></span>

    1. <span data-ttu-id="da2cb-124">`binding`요소의 특성을로 설정 [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-element.md) `customBinding` 합니다.</span><span class="sxs-lookup"><span data-stu-id="da2cb-124">Set the `binding` attribute of the [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-element.md) element to `customBinding`.</span></span>

    2. <span data-ttu-id="da2cb-125">`bindingConfiguration`요소의 특성을 [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-element.md) `name` [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) 사용자 지정 바인딩에 대 한의 특성에 지정 된 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="da2cb-125">Set the `bindingConfiguration` attribute of the [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-element.md) element to the value specified in the `name` attribute of the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) for the custom binding.</span></span>

## <a name="example"></a><span data-ttu-id="da2cb-126">예제</span><span class="sxs-lookup"><span data-stu-id="da2cb-126">Example</span></span>

<span data-ttu-id="da2cb-127">다음은 `Service.HelloWorldService`에서 사용자 지정 바인딩을 사용하여 WSE 3.0 클라이언트와 상호 운용하도록 지정하는 코드 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="da2cb-127">The following code example specifies that the `Service.HelloWorldService` uses a custom binding to interoperate with WSE 3.0 clients.</span></span> <span data-ttu-id="da2cb-128">사용자 지정 바인딩에서는 교환되는 메시지를 인코딩하는 데 2004년 8월 버전의 WS-Addressing과 WS-Security 1.1을 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="da2cb-128">The custom binding specifies that the August 2004 version of the WS-Addressing and the WS-Security 1.1 set of specifications are used to encode the exchanged messages.</span></span> <span data-ttu-id="da2cb-129">메시지 보안은 <xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate> 인증 모드를 통해 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="da2cb-129">The messages are secured using the <xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate> authentication mode.</span></span>

```xml
<configuration>
  <system.serviceModel>
    <services>
      <service
        behaviorConfiguration="ServiceBehavior"
        name="Service.HelloWorldService">
        <endpoint binding="customBinding" address=""
          bindingConfiguration="ServiceBinding"
          contract="Service.IHelloWorld"></endpoint>
      </service>
    </services>

    <bindings>
      <customBinding>
        <binding name="ServiceBinding">
          <security authenticationMode="AnonymousForCertificate"
                  messageProtectionOrder="SignBeforeEncrypt"
                  messageSecurityVersion="WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10"
                  requireDerivedKeys="false">
          </security>
          <textMessageEncoding messageVersion ="Soap11WSAddressingAugust2004"></textMessageEncoding>
          <httpTransport/>
        </binding>
      </customBinding>
    </bindings>
    <behaviors>
      <behavior name="ServiceBehavior" returnUnknownExceptionsAsFaults="true">
        <serviceCredentials>
          <serviceCertificate findValue="CN=WCFQuickstartServer" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectDistinguishedName"/>
        </serviceCredentials>
      </behavior>
    </behaviors>
  </system.serviceModel>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="da2cb-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="da2cb-130">See also</span></span>

- [<span data-ttu-id="da2cb-131">방법: 시스템 제공 바인딩 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="da2cb-131">How to: Customize a System-Provided Binding</span></span>](../extending/how-to-customize-a-system-provided-binding.md)
