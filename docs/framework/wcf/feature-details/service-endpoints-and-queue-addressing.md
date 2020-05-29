---
title: 서비스 엔드포인트 및 큐 주소 지정
ms.date: 03/30/2017
ms.assetid: 7d2d59d7-f08b-44ed-bd31-913908b83d97
ms.openlocfilehash: 8b323993a698dac219e0f2be43e9b508a19065dd
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202420"
---
# <a name="service-endpoints-and-queue-addressing"></a>서비스 엔드포인트 및 큐 주소 지정
이 항목에서는 클라이언트가 큐에서 읽는 서비스에 주소를 지정하는 방법 및 서비스 엔드포인트가 큐에 매핑되는 방법을 설명합니다. 다음 그림에서는 미리 알림을 통해 기존 WCF (Windows Communication Foundation) 대기 중인 응용 프로그램 배포를 보여 줍니다.  
  
 ![대기 중인 응용 프로그램 다이어그램](../../../../docs/framework/wcf/feature-details/media/distributed-queue-figure.jpg "분산 큐 그림")  
  
 클라이언트가 서비스에 메시지를 보낼 수 있도록 하려면 대상 큐에 메시지 주소를 지정합니다. 서비스가 큐에서 메시지를 읽을 수 있도록 하려면 해당 수신 주소를 대상 큐로 설정합니다. WCF의 주소 지정은 uri (Uniform Resource Identifier) 기반 이지만 메시지 큐 (MSMQ) 큐 이름은 URI 기반이 아닙니다. 따라서 WCF를 사용 하 여 MSMQ에서 만든 큐를 처리 하는 방법을 이해 하는 것이 중요 합니다.  
  
## <a name="msmq-addressing"></a>MSMQ 주소 지정  
 MSMQ는 경로 및 형식 이름을 사용하여 큐를 식별합니다. 경로는 호스트 이름 및 `QueueName`을 지정합니다. 필요한 경우 호스트 이름과 `Private$` 간에 Active Directory 디렉터리 서비스에 게시되지 않은 개인 큐를 나타내도록 `QueueName`가 있을 수 있습니다.  
  
 경로 이름은 라우팅 및 큐 관리자 전송 프로토콜을 포함 하 여 주소의 추가 측면을 결정 하기 위해 "FormatNames"에 매핑됩니다. 큐 관리자는 기본 MSMQ 프로토콜과 SRMP(SOAP Reliable Messaging Protocol)의 두 가지 전송 프로토콜을 지원합니다.  
  
 MSMQ 경로 및 형식 이름에 대 한 자세한 내용은 [메시지 큐 정보](https://docs.microsoft.com/previous-versions/windows/desktop/legacy/ms706032(v=vs.85))를 참조 하세요.  
  
## <a name="netmsmqbinding-and-service-addressing"></a>NetMsmqBinding 및 서비스 주소 지정  
 서비스로 메시지 주소를 지정할 때 URI의 체계는 통신에 사용되는 전송에 따라 선택됩니다. WCF의 각 전송에는 고유한 체계가 있습니다. 체계는 통신에 사용되는 전송의 특성을 반영해야 합니다. 예를 들어 net.tcp, net.pipe, HTTP 등입니다.  
  
 WCF의 MSMQ 대기 중인 전송에서는 net.pipe 스키마를 제공 합니다. net.msmq 체계를 사용하여 주소가 지정된 메시지는 MSMQ 대기 중인 전송 채널을 통해 `NetMsmqBinding`을 사용하여 보내집니다.  
  
 WCF에서 큐 주소 지정은 다음 패턴을 기반으로 합니다.  
  
 net.pipe:// \<*host-name*> /[private/]\<*queue-name*>  
  
 여기서  
  
- \<*host-name*>대상 큐를 호스팅하는 컴퓨터의 이름입니다.  
  
- [private]는 선택 사항입니다. 개인 큐인 대상 큐에 주소를 지정할 때 사용됩니다. 공개 큐에 주소를 지정하려면 private를 지정하지 않아야 합니다. MSMQ 경로와 달리 WCF URI 형식에는 "$"가 없습니다.  
  
- \<*queue-name*>큐의 이름입니다. 큐 이름은 하위 큐를 참조할 수도 있습니다. 따라서 \<*queue-name*>  =  \<*name-of-queue*> [;* 하위 큐-이름*].  
  
 예제 1: abc atadatum.com 컴퓨터에서 호스팅된 개인 큐 PurchaseOrders에 주소를 지정하는 경우 URI는 net.msmq://abc.adatum.com/private/PurchaseOrders입니다.  
  
 예제 2: def atadatum.com 컴퓨터에서 호스팅된 공개 큐 AccountsPayable에 주소를 지정하는 경우 URI는 net.msmq://def.adatum.com/AccountsPayable입니다.  
  
 큐 주소는 메시지를 읽을 수신기에 의해 수신 대기 URI로 사용됩니다. 즉, 큐 주소는 TCP 소켓의 수신 대기 포트에 해당합니다.  
  
 큐에서 읽는 엔드포인트에서는 ServiceHost를 열 때 이전에 지정한 같은 체계를 사용하여 큐의 주소를 지정해야 합니다. 예제는 [NET MSMQ 바인딩](../../../../docs/framework/wcf/samples/net-msmq-binding.md)을 참조 하세요.  
  
### <a name="multiple-contracts-in-a-queue"></a>큐의 여러 계약  
 큐의 메시지는 서로 다른 계약을 구현할 수 있습니다. 이 경우 다음 중 하나가 충족되어야 모든 메시지를 읽고 처리할 수 있습니다.  
  
- 모든 계약을 구현하는 서비스 엔드포인트를 지정합니다. 이 방법을 사용하는 것이 좋습니다.  
  
- 서로 다른 계약으로 여러 엔드포인트를 지정하지만 모든 엔드포인트가 같은 `NetMsmqBinding` 개체를 사용해야 합니다. ServiceModel에서 디스패치 논리는 디스패치용 전송 채널에서 메시지를 읽는 메시지 펌프를 사용하므로, 서로 다른 엔드포인트로 계약 기반 메시지를 역 멀티플렉싱합니다. 메시지 펌프는 수신 대기 URI/바인딩 쌍에 대해 만들어집니다. 큐 주소는 대기 중인 수신기에 의해 수신 대기 URI로 사용됩니다. 모든 엔드포인트가 같은 바인딩 개체를 사용하는 경우 단일 메시지 펌프가 메시지를 읽고 계약을 기반으로 관련 엔드포인트에 역 멀티플렉싱하는 데 사용됩니다.  
  
### <a name="srmp-messaging"></a>SRMP 메시징  
 앞에서 설명한 대로 큐 간 전송에 SRMP 프로토콜을 사용할 수 있습니다. 일반적으로 이 방법은 HTTP 전송이 전송 큐와 대상 큐 간에 메시지를 전송할 때 사용됩니다.  
  
 SRMP 전송 프로토콜을 사용하려면 앞에서 언급했듯이 net.msmq URI 체계를 사용하여 메시지에 주소를 지정하고 `QueueTransferProtocol`의 `NetMsmqBinding` 속성에 SRMP 또는 보안 SRMP를 지정합니다.  
  
 `QueueTransferProtocol` 속성을 지정하면 보내기 전용 기능이 됩니다. 이것은 클라이언트가 사용할 큐 전송 프로토콜의 종류를 나타냅니다.  
  
### <a name="using-active-directory"></a>Active Directory 사용  
 MSMQ에는 Active Directory 통합에 대한 지원이 포함되어 있습니다. MSMQ가 Active Directory 통합과 함께 설치되는 경우 해당 컴퓨터는 Windows 도메인에 속해야 합니다. Active Directory는 검색을 위해 큐를 게시 하는 데 사용 됩니다. 이러한 큐를 *공개 큐*라고 합니다. 큐에 주소를 지정할 때 Active Directory를 사용하여 해당 큐를 확인할 수 있습니다. 이 방법은 네트워크 이름의 IP 주소를 확인할 때 DNS(Domain Name System)를 사용하는 방법과 비슷합니다. `UseActiveDirectory`의 `NetMsmqBinding` 속성은 대기 중인 채널이 Active Directory를 사용하여 큐 URI를 확인해야 하는지 여부를 나타내는 부울입니다. 기본적으로 이 속성은 `false`로 설정됩니다. `UseActiveDirectory` 속성이 `true`로 설정되는 경우 대기 중인 채널은 Active Directory를 사용하여 net.msmq:// URI를 형식 이름으로 변환합니다.  
  
 `UseActiveDirectory` 속성이 메시지를 보낼 때 큐의 주소를 확인하는 데 사용되므로 메시지를 보내는 클라이언트에 대해서만 설정할 수 있습니다.  
  
### <a name="mapping-netmsmq-uri-to-message-queuing-format-names"></a>메시지 큐 형식 이름에 net.msmq URI 매핑  
 대기 중인 채널에서 채널에 제공된 net.msmq URI 이름을 MSMQ 형식 이름으로 매핑하는 작업을 처리합니다. 다음 표에서는 이들 간 매핑에 사용된 규칙을 요약하여 설명합니다.  
  
|WCF URI 기반 큐 주소|Active Directory 속성 사용|큐 전송 프로토콜 속성|결과 MSMQ 형식 이름|  
|----------------------------------|-----------------------------------|--------------------------------------|---------------------------------|  
|`Net.msmq://<machine-name>/private/abc`|False(기본값)|Native(기본값)|`DIRECT=OS:machine-name\private$\abc`|  
|`Net.msmq://<machine-name>/private/abc`|False|SRMP|`DIRECT=http://machine/msmq/private$/abc`|  
|`Net.msmq://<machine-name>/private/abc`|True|기본|`PUBLIC=some-guid`(큐의 GUID)|  
  
### <a name="reading-messages-from-the-dead-letter-queue-or-the-poison-message-queue"></a>배달 못 한 편지 큐 또는 포이즌 메시지 큐에서 메시지 읽기  
 대상 큐의 하위 큐인 포이즌 메시지 큐에서 메시지를 읽으려면 하위 큐의 주소가 있는 `ServiceHost`를 엽니다.  
  
 예제: 로컬 컴퓨터에 있는 개인 큐 PurchaseOrders의 포이즌 메시지 큐에서 읽는 서비스는 net.msmq://localhost/private/PurchaseOrders;poison 주소를 지정합니다.  
  
 시스템 트랜잭션 배달 못 한 편지 큐에서 메시지를 읽으려면 URI가 net.msmq://localhost/system$;DeadXact 형식이어야 합니다.  
  
 시스템 비트랜잭션 배달 못 한 편지 큐에서 메시지를 읽으려면 URI가 net.msmq://localhost/system$;DeadLetter 형식이어야 합니다.  
  
 사용자 지정 배달 못 한 편지 큐를 사용할 때 배달 못 한 편지 큐가 로컬 컴퓨터에 있어야 합니다. 따라서 배달 못 한 편지 큐의 URI는 다음 형식으로 제한됩니다.  
  
 net.pipe:/localhost/[private/] \<*custom-dead-letter-queue-name*> .  
  
 WCF 서비스는 수신 하는 모든 메시지가 수신 대기 중인 특정 큐로 주소가 지정 되었는지 확인 합니다. 메시지의 대상 큐가 메시지가 있는 큐와 일치하지 않으면 서비스가 메시지를 처리하지 않습니다. 이 경우 배달 못 한 편지 큐의 메시지를 다른 곳으로 배달해야 하므로 배달 못 한 편지 큐를 수신하는 서비스가 주소를 지정해야 하는 문제가 있습니다. 배달 못 한 편지 큐에서 또는 포이즌 큐에서 메시지를 읽으려면 `ServiceBehavior` 매개 변수를 포함하는 <xref:System.ServiceModel.AddressFilterMode.Any>를 사용해야 합니다. 예를 들어 [배달 못한 편지 큐](../../../../docs/framework/wcf/samples/dead-letter-queues.md)를 참조 하십시오.  
  
## <a name="msmqintegrationbinding-and-service-addressing"></a>MsmqIntegrationBinding 및 서비스 주소 지정  
 `MsmqIntegrationBinding`은 기존 MSMQ 애플리케이션과의 통신에 사용됩니다. 기존 MSMQ 응용 프로그램과의 상호 작용을 용이 하 게 하기 위해 WCF는 형식 이름 주소 지정만 지원 합니다. 따라서 이 바인딩을 사용하여 보낸 메시지는 URI 체계를 따라야 합니다.  
  
 msmq.formatname:\<*MSMQ-format-name*>>  
  
 MSMQ 형식의 이름은 MSMQ에서 [메시지 큐에 대해](https://docs.microsoft.com/previous-versions/windows/desktop/legacy/ms706032(v=vs.85))지정 하는 형식입니다.  
  
 `MsmqIntegrationBinding`을 사용하여 큐에서 메시지를 받을 때 직접 형식 이름, 공개 및 개인 형식 이름만 사용할 수 있습니다(Active Directory 통합 필요). 그러나 직접 형식 이름을 사용하는 것이 좋습니다. 예를 들어 Windows Vista에서 다른 형식 이름을 사용 하면 시스템에서 직접 형식 이름 으로만 열 수 있는 하위 큐를 열려고 하기 때문에 오류가 발생 합니다.  
  
 `MsmqIntegrationBinding`을 사용하여 SRMP에 주소를 지정할 때 IIS(인터넷 정보 서비스)가 디스패치할 수 있도록 직접 형식 이름에 /msmq/를 추가하지 않아도 됩니다. 예: SRMP 프로토콜을 사용 하 여 큐 abc의 주소를 지정 하는 경우 대신를 `DIRECT=http://adatum.com/msmq/private$/abc` 사용 해야 `DIRECT=http://adatum.com/private$/abc` 합니다.  
  
 `MsmqIntegrationBinding`과 함께 net.msmq:// 주소 지정을 사용할 수 없습니다. 는 `MsmqIntegrationBinding` 자유 형식 msmq 형식 이름 주소 지정을 지원 하므로이 바인딩을 사용 하는 WCF 서비스를 사용 하 여 msmq에서 멀티 캐스트 및 메일 그룹 기능을 사용할 수 있습니다. 한 가지 예외의 경우는 `CustomDeadLetterQueue`을 사용할 때 `MsmqIntegrationBinding`를 지정하는 것입니다. 이 경우 net.msmq:// 형식이어야 하며, `NetMsmqBinding`을 사용하여 지정하는 방법과 비슷합니다.  
  
## <a name="see-also"></a>참고 항목

- [대기 중인 애플리케이션 웹 호스팅](../../../../docs/framework/wcf/feature-details/web-hosting-a-queued-application.md)
