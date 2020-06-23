---
title: 바인딩 및 보안
description: 보안 요구 사항에 적합 한 바인딩을 선택 하는 방법을 알아보세요. WCF에 포함 된 시스템 제공 바인딩은 WCF 응용 프로그램을 신속 하 게 프로그래밍 하는 방법을 제공 합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- bindings [WCF], security
- WCF security
- Windows Communication Foundation, security
- bindings [WCF]
ms.assetid: 4de03dd3-968a-4e65-af43-516e903d7f95
ms.openlocfilehash: e012ec9ad340c74f5bc776cfc6d8b88326210fec
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245337"
---
# <a name="bindings-and-security"></a>바인딩 및 보안

WCF (Windows Communication Foundation)에 포함 된 시스템 제공 바인딩은 WCF 응용 프로그램을 신속 하 게 프로그래밍할 수 있는 방법을 제공 합니다. 한 가지 예외를 통해 모든 바인딩의 기본 보안 스키마가 활성화됩니다. 이 항목은 보안 요구 사항에 적합한 바인딩을 선택하는 데 도움을 줍니다.

WCF 보안에 대 한 개요는 [보안 개요](security-overview.md)를 참조 하세요. 바인딩을 사용 하 여 WCF를 프로그래밍 하는 방법에 대 한 자세한 내용은 [Wcf 보안 프로그래밍](programming-wcf-security.md)을 참조 하세요.

바인딩을 이미 선택한 경우 [보안 동작](security-behaviors-in-wcf.md)의 보안과 관련 된 런타임 동작에 대 한 자세한 내용을 확인할 수 있습니다.

일부 보안 기능은 시스템 제공 바인딩을 사용하여 프로그래밍할 수 없습니다. 사용자 지정 바인딩을 사용 하는 더 많은 제어를 위해 [사용자 지정 바인딩을](security-capabilities-with-custom-bindings.md)사용 하는 보안 기능을 참조 하세요.

## <a name="security-functions-of-bindings"></a>바인딩의 보안 기능

WCF에는 대부분의 요구를 충족 하는 여러 시스템 제공 바인딩이 포함 되어 있습니다. 또한 특정 바인딩이 요구 사항을 충족하지 않는 경우, 사용자 지정 바인딩을 만들 수도 있습니다. 시스템 제공 바인딩 목록은 [시스템 제공 바인딩](../system-provided-bindings.md)을 참조 하세요. 사용자 지정 바인딩에 대 한 자세한 내용은 [사용자 지정 바인딩](../extending/custom-bindings.md)을 참조 하세요.

WCF의 모든 바인딩에는 API와 구성 파일에 사용 되는 XML 요소로 구성 된 두 가지 형식이 있습니다. 예를 들어 `WSHttpBinding` (API)에는에 해당 하는이 [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) 있습니다.

다음 단원에서는 각 바인딩에 대한 두 가지 양식을 나열하고 해당 보안 기능에 대해 요약하여 설명합니다.

### <a name="basichttp"></a>BasicHttp

코드에서 클래스를 사용 <xref:System.ServiceModel.BasicHttpBinding> 합니다. 구성에서를 사용 [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) 합니다.

이 바인딩은 다음을 포함하여 일정 범위의 기존 기술을 사용하도록 디자인되었습니다.

- ASP.NET 웹 서비스(ASMX), 버전 1

- WSE(Web Service Enhancement) 애플리케이션

- WS (웹 서비스 상호 운용성) 사양 ()에 정의 된 기본 프로필 <https://go.microsoft.com/fwlink/?LinkId=38955> 입니다.

- WS-I에 정의된 기본 보안 프로필

기본적으로 이 바인딩은 보안 처리되어 있지 않습니다. ASMX 서비스와 상호 운용되도록 디자인되었습니다. 보안을 사용하는 경우 바인딩은 기본 인증, 다이제스트 및 통합 Windows 보안과 같이 IIS(인터넷 정보 서비스) 보안 메커니즘과 원활한 상호 운용을 위해 디자인됩니다. 자세한 내용은 [전송 보안 개요](transport-security-overview.md)를 참조 하세요. 이 바인딩은 다음을 지원합니다.

- HTTPS 전송 보안.

- HTTP 기본 인증.

- WS-Security.

자세한 내용은 다음을 참조하세요.<xref:System.ServiceModel.BasicHttpSecurity>, <xref:System.ServiceModel.BasicHttpMessageSecurity>, <xref:System.ServiceModel.BasicHttpMessageCredentialType> 및 <xref:System.ServiceModel.BasicHttpSecurityMode>.

### <a name="wshttpbinding"></a>WSHttpBinding

코드에서 클래스를 사용 <xref:System.ServiceModel.WSHttpBinding> 합니다. 구성에서를 사용 [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) 합니다.

기본적으로 이 바인딩은 WS-Security 사양을 구현하고 WS-* 사양을 구현하는 서비스와의 상호 운용성을 제공합니다. 다음을 지원합니다.

- HTTPS 전송 보안.

- WS-Security.

- 호출자를 인증하기 위한 SOAP 메시지 자격 증명 보안을 사용하여 HTTPS 전송 보호.

자세한 내용은,,,,, 및를 참조 하십시오 <xref:System.ServiceModel.WSHttpSecurity> <xref:System.ServiceModel.MessageSecurityOverHttp> <xref:System.ServiceModel.MessageCredentialType> <xref:System.ServiceModel.SecurityMode> <xref:System.ServiceModel.HttpTransportSecurity> <xref:System.ServiceModel.HttpClientCredentialType> <xref:System.ServiceModel.HttpProxyCredentialType> .

### <a name="wsdualhttpbinding"></a>WSDualHttpBinding

코드에서 클래스를 사용 <xref:System.ServiceModel.WSDualHttpBinding> 합니다. 구성에서를 사용 [\<wsDualHttpBinding>](../../configure-apps/file-schema/wcf/wsdualhttpbinding.md) 합니다.

이 바인딩은 이중 서비스 애플리케이션을 사용하도록 디자인되었습니다. 이 바인딩은 메시지 기반 전송 보안을 위한 WS-Security 사양을 구현합니다. 전송 보안을 사용할 수 없습니다. 기본적으로 다음 기능을 제공합니다.

- 안정성을 위해 WS-Reliable Messaging을 구현합니다.

- 전송 보안 및 인증을 위해 WS-Security를 구현합니다.

- 메시지 배달을 위해 HTTP를 사용합니다.

- 텍스트/XML 메시지 인코딩을 사용합니다.

 WS-Security(메시지 계층 보안)를 사용하면 바인딩을 통해 다음 매개 변수를 구성할 수 있습니다.

- 암호화 알고리즘을 결정하기 위한 보안 알고리즘 모음.

- 다음에 대한 바인딩 옵션.

  - 클라이언트에서 서비스 자격 증명 사용 가능한 out-of-band를 제공하는 경우.

  - 채널 설정의 일부로 서비스에서 협상된 서비스 자격 증명을 제공하는 경우.

자세한 내용은 <xref:System.ServiceModel.WSDualHttpSecurity> 및 <xref:System.ServiceModel.WSDualHttpSecurityMode>를 참조하세요.

### <a name="nettcpbinding"></a>NetTcpBinding

코드에서 클래스를 사용 <xref:System.ServiceModel.NetTcpBinding> 합니다. 구성에서를 사용 [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md) 합니다.

이 바인딩은 시스템 간 통신을 위해 최적화됩니다. 기본적으로 다음과 같은 특성이 있습니다.

- 전송 계층 보안을 구현합니다.

- 전송 보안 및 인증을 위해 Windows 보안을 사용합니다.

- 전송을 위해 TCP를 사용합니다.

- 이진 메시지 인코딩을 구현합니다.

- WS-Reliable Messaging을 구현합니다.

다음과 같은 옵션을 사용할 수 있습니다.

- 메시지 계층 보안(WS-Security 사용).

- 메시지 자격 증명을 통한 전송 보안—TCP를 통한 TLS(전송 계층 보안)에 의해 제공되는 기밀성과 무결성 및 WS-Security에 의해 제공되는 권한에 대한 자격 증명.

자세한 내용은,,, 및를 참조 하십시오 <xref:System.ServiceModel.NetTcpSecurity> <xref:System.ServiceModel.TcpTransportSecurity> <xref:System.ServiceModel.TcpClientCredentialType> <xref:System.ServiceModel.MessageSecurityOverTcp> <xref:System.ServiceModel.MessageCredentialType> .

### <a name="netnamedpipebinding"></a>NetNamedPipeBinding

코드에서 클래스를 사용 <xref:System.ServiceModel.NetNamedPipeBinding> 합니다. 구성에서를 사용 [\<netNamedPipeBinding>](../../configure-apps/file-schema/wcf/netnamedpipebinding.md) 합니다.

이 바인딩은 일반적으로 동일한 시스템에서의 프로세스 간 통신을 위해 최적화됩니다. 기본적으로 이 바인딩에는 다음과 같은 특성이 있습니다.

- 메시지 전송 및 인증을 위해 전송 보안을 사용합니다.

- 메시지 배달을 위해 명명된 파이프를 사용합니다.

- 이진 메시지 인코딩을 구현합니다.

- 암호화 및 메시지 서명.

다음과 같은 옵션을 사용할 수 있습니다.

- Windows 보안을 사용하여 인증.

자세한 내용은 <xref:System.ServiceModel.NetNamedPipeSecurity>, <xref:System.ServiceModel.NetNamedPipeSecurityMode> 및 <xref:System.ServiceModel.NamedPipeTransportSecurity>을 참조하십시오.

### <a name="msmqintegrationbinding"></a>MsmqIntegrationBinding

코드에서 클래스를 사용 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> 합니다. 구성에서를 사용 [\<msmqIntegrationBinding>](../../configure-apps/file-schema/wcf/msmqintegrationbinding.md) 합니다.

이 바인딩은 wcf (Microsoft Message Queuing)가 아닌 MSMQ (Microsoft Message Queuing) 끝점과 상호 작용 하는 WCF 클라이언트 및 서비스를 만드는 데 최적화 되어 있습니다.

기본적으로 이 바인딩은 전송 보안을 사용하고 다음과 같은 보안 특성을 제공합니다.

- 보안을 사용할 수 없습니다(None).

- MSMQ 전송 보안입니다(Transport).

자세한 내용은 <xref:System.ServiceModel.NetMsmqSecurity> 및 <xref:System.ServiceModel.NetMsmqSecurityMode>를 참조하세요.

### <a name="netmsmqbinding"></a>NetMsmqBinding

코드에서 클래스를 사용 <xref:System.ServiceModel.NetMsmqBinding> 합니다. 구성에서를 사용 [\<netMsmqBinding>](../../configure-apps/file-schema/wcf/netmsmqbinding.md) 합니다.

이 바인딩은 MSMQ 큐에 대기 중인 메시지를 지원 해야 하는 WCF 서비스를 만들 때 사용 됩니다.

기본적으로 이 바인딩은 전송 보안을 사용하고 다음과 같은 보안 특성을 제공합니다.

- 보안을 사용할 수 없습니다(None).

- MSMQ 전송 보안입니다(Transport).

- SOAP 기반 메시지 보안입니다(Message).

- 동시 전송 및 메시지 보안입니다(Both).

- 지원되는 클라이언트 자격 증명 형식: None, Windows, UserName, Certificate, IssuedToken

<xref:System.ServiceModel.MessageCredentialType.Certificate> 자격 증명은 보안 모드를 <xref:System.ServiceModel.NetMsmqSecurityMode.Both> 또는 <xref:System.ServiceModel.NetMsmqSecurityMode.Message> 중 하나로 설정하는 경우에만 지원됩니다.

자세한 내용은 <xref:System.ServiceModel.MessageSecurityOverMsmq> 및 <xref:System.ServiceModel.MsmqTransportSecurity>를 참조하세요.

### <a name="wsfederationhttpbinding"></a>WSFederationHttpBinding

코드에서 클래스를 사용 <xref:System.ServiceModel.WSFederationHttpBinding> 합니다. 구성에서를 사용 [\<wsFederationHttpBinding>](../../configure-apps/file-schema/wcf/wsfederationhttpbinding.md) 합니다.

기본적으로 이 바인딩은 WS-Security(메시지 계층 보안)를 사용합니다.

자세한 내용은 [페더레이션](federation.md), 및을 참조 하세요 <xref:System.ServiceModel.WSFederationHttpSecurity> <xref:System.ServiceModel.WSFederationHttpSecurityMode> .

## <a name="custom-bindings"></a>사용자 지정 바인딩

시스템 제공 바인딩이 요구 사항을 충족하지 못하는 경우 사용자 지정 보안 바인딩 요소를 사용하여 사용자 지정 바인딩을 만들 수 있습니다. 자세한 내용은 [사용자 지정 바인딩을 사용 하는 보안 기능](security-capabilities-with-custom-bindings.md)을 참조 하세요.

## <a name="binding-choices"></a>바인딩 선택

다음 표에서는 보안 모드 설정에서 제공하는 기능에 대해 요약하여 설명합니다. 즉, 보안 모드를 `Transport`, `Message` 또는 `TransportWithMessageCredential`로 설정한 경우 사용할 수 있는 기능을 보여 줍니다. 이 표를 사용하면 애플리케이션에서 필요한 보안 기능을 찾는 데 도움을 줍니다.

|설정|기능|
|-------------|--------------|
|전송|서버 인증<br /><br /> 클라이언트 인증<br /><br /> 지점 간 보안<br /><br /> 상호 운용성<br /><br /> 하드웨어 가속<br /><br /> 높은 처리량<br /><br /> 보안 방화벽<br /><br /> 대기 시간이 긴 애플리케이션<br /><br /> 여러 홉을 통해 다시 암호화|
|메시지|서버 인증<br /><br /> 클라이언트 인증<br /><br /> 엔드투엔드 보안<br /><br /> 상호 운용성<br /><br /> 다양한 클레임<br /><br /> 페더레이션<br /><br /> Multi-Factor Authentication<br /><br /> 사용자 지정 토큰<br /><br /> 공증/타임스탬프 서비스<br /><br /> 대기 시간이 긴 애플리케이션<br /><br /> 메시지 서명 지속성|
|TransportWithMessageCredential|서버 인증<br /><br /> 클라이언트 인증<br /><br /> 지점 간 보안<br /><br /> 상호 운용성<br /><br /> 하드웨어 가속<br /><br /> 높은 처리량<br /><br /> 다양한 클라이언트 클레임<br /><br /> 페더레이션<br /><br /> Multi-Factor Authentication<br /><br /> 사용자 지정 토큰<br /><br /> 보안 방화벽<br /><br /> 대기 시간이 긴 애플리케이션<br /><br /> 여러 홉을 통해 다시 암호화|

다음 표에서는 다양한 모드 설정을 지원하는 바인딩을 보여 줍니다. 표에서 서비스 엔드포인트를 만드는 데 사용할 바인딩을 선택합니다.

|바인딩|Transport 모드 지원|Message 모드 지원|TransportWithMessageCredential 지원|
|-------------|----------------------------|--------------------------|--------------------------------------------|
|`BasicHttpBinding`|Yes|Yes|Yes|
|`WSHttpBinding`|Yes|Yes|예|
|`WSDualHttpBinding`|예|예|예|
|`NetTcpBinding`|예|Yes|Yes|
|`NetNamedPipeBinding`|예|아니요|예|
|`NetMsmqBinding`|예|예|예|
|`MsmqIntegrationBinding`|예|아니요|아니요|
|`wsFederationHttpBinding`|예|예|Yes|

## <a name="transport-credentials-in-bindings"></a>바인딩의 전송 자격 증명

다음 표에서는 전송 보안 모드에서 `BasicHttpBinding` 또는 `WSHttpBinding` 사용 시 사용할 수 있는 클라이언트 자격 증명 형식을 보여 줍니다.

|Type|Description|
|----------|-----------------|
|None|클라이언트가 자격 증명을 제공할 필요가 없음을 지정합니다. 익명 클라이언트로 변환됩니다.|
|Basic|기본 인증입니다. 자세한 내용은 RFC 2617 – HTTP 인증: 기본 및 다이제스트 인증 (에서 사용 가능)을 참조 하세요 <https://go.microsoft.com/fwlink/?LinkId=84023> .|
|다이제스트|다이제스트 인증입니다. 자세한 내용은 RFC 2617 – HTTP 인증: 기본 및 다이제스트 인증 (에서 사용 가능)을 참조 하세요 <https://go.microsoft.com/fwlink/?LinkId=84023> .|
|NTLM|NTLM(NT LAN Manager) 인증입니다.|
|Windows|Windows 인증입니다.|
|인증서|인증서를 사용하여 수행되는 인증입니다.|
|IssuedToken|서비스에서 보안 토큰 서비스 또는 CardSpace가 발급 한 토큰을 사용 하 여 클라이언트를 인증 하도록 요구할 수 있습니다. 자세한 내용은 [페더레이션 및 발급 된 토큰](federation-and-issued-tokens.md)을 참조 하세요.|

### <a name="message-client-credentials-in-bindings"></a>바인딩의 메시지 클라이언트 자격 증명

다음 표에서는 메시지 보안 모드에서 바인딩 사용 시 사용할 수 있는 클라이언트 자격 증명 형식을 보여 줍니다.

|Type|Description|
|----------|-----------------|
|None|서비스와 익명 클라이언트가 상호 작용할 수 있습니다.|
|Windows|Windows 자격 증명의 인증된 컨텍스트에서 SOAP 메시지 교환을 수행할 수 있습니다.|
|UserName|서비스에서 사용자 이름 자격 증명을 사용하여 클라이언트를 인증하도록 요구할 수 있습니다. 보안 모드가로 설정 된 경우 WCF는 암호 `TransportWithMessageCredential` 다이제스트를 보내거나 암호를 사용 하 여 키를 파생 하 고 메시지 모드 보안에 이러한 키를 사용 하는 것을 지원 하지 않습니다. 따라서 WCF는 사용자 이름 자격 증명을 사용할 때 전송에 보안을 적용 합니다.|
|인증서|서비스에서 인증서를 사용하여 클라이언트를 인증하도록 요구할 수 있습니다.|
|IssuedToken|서비스가 보안 토큰 서비스를 사용하여 사용자 지정 토큰을 제공할 수 있습니다.|

## <a name="see-also"></a>참고 항목

- [보안 개요](security-overview.md)
- [서비스 및 클라이언트에 보안 설정](securing-services-and-clients.md)
- [자격 증명 형식 선택](selecting-a-credential-type.md)
- [사용자 지정 바인딩을 사용하는 보안 기능](security-capabilities-with-custom-bindings.md)
- [보안 동작](security-behaviors-in-wcf.md)
- [Windows Server AppFabric 보안 모델](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
