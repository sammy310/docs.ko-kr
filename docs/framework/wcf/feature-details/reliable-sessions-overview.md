---
description: '자세한 정보: 신뢰할 수 있는 세션 개요'
title: 신뢰할 수 있는 세션 개요
ms.date: 03/30/2017
ms.assetid: a7fc4146-ee2c-444c-82d4-ef6faffccc2d
ms.openlocfilehash: 51de6012245b4fc0a367069d02fe69ee031f2b30
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99632895"
---
# <a name="reliable-sessions-overview"></a>신뢰할 수 있는 세션 개요

WCF (Windows Communication Foundation) SOAP 신뢰할 수 있는 메시징은 SOAP 끝점 간의 종단 간 메시지 전송 안정성을 제공 합니다. 전송 오류 및 SOAP 메시지 수준 오류를 극복하여 신뢰할 수 없는 네트워크에서 이를 구현합니다. 특히 SOAP 또는 전송 매개자를 통해 보낸 메시지에 대해 세션 기반, 단일 및 필요에 따라 순서가 지정된 배달을 제공합니다. 세션 기반 배달은 메시지를 선택적으로 정렬 하 여 세션에서 메시지를 그룹화 하는 기능을 제공 합니다.

이 항목에서는 신뢰할 수 있는 세션, 사용 방법 및 사용 시기와 이러한 세션을 보호 하는 방법을 설명 합니다.

## <a name="wcf-reliable-sessions"></a>WCF 신뢰할 수 있는 세션

WCF 신뢰할 수 있는 세션은 WS-ReliableMessaging 프로토콜에서 정의한 SOAP 신뢰할 수 있는 메시징 구현입니다.

WCF SOAP 신뢰할 수 있는 메시징은 메시징 끝점을 분리 하는 중개의 수 나 유형에 관계 없이 두 끝점 사이에 종단 간 신뢰할 수 있는 세션을 제공 합니다. 여기에는 끝점 간에 메시지를 전달 하는 데 필요한 soap (예: HTTP 프록시) 또는 soap를 사용 하는 중개 (예: SOAP 기반 라우터 또는 브리지)를 사용 하지 않는 모든 전송 중개자가 포함 됩니다. 신뢰할 수 있는 세션 채널은 이러한 채널에서 연결 된 서비스가 동시에 실행 되 고 짧은 대기 시간, 즉 비교적 짧은 시간 간격 내에서 메시지를 교환 하 고 처리 하도록 *대화형* 통신을 지원 합니다. 이러한 결합은 이러한 구성 요소가 함께 진행 되거나 장애 조치 (failover) 되는 것을 의미 하기 때문에 격리를 제공 하지 않습니다.

신뢰할 수 있는 세션에서는 다음 두 가지 유형의 오류를 마스킹합니다.

- 손실되거나 중복된 메시지 및 보낸 순서와 다른 순서로 도착한 메시지를 포함하는 SOAP 메시지 수준 오류

- 전송 오류

신뢰할 수 있는 세션은 WS-ReliableMessaging 프로토콜 및 내장 메모리 전송 창을 구현하여 SOAP 메시지 수준 오류를 마스킹하고 전송 오류가 발생할 경우 다시 연결합니다.

신뢰할 수 있는 세션은 TCP가 IP 패킷에 대해 제공하는 SOAP 메시지를 제공합니다. TCP 소켓 연결은 노드 간에 IP 패킷에 대한 단수형의 순서가 지정된 전송을 제공합니다. 신뢰할 수 있는 채널은 신뢰할 수 있는 전송과 동일한 유형을 제공하지만 다음과 같은 방법에서 TCP 소켓 안정성이 다릅니다.

- 안정성은 임의 크기 패킷(바이트)이 아닌 SOAP 메시지 수준에서 구현됩니다.

- 안정성은 TCP를 통한 전송 뿐만 아니라 전송 중립적입니다.

- 안정성은 특정 전송 세션 (예: TCP 연결이 제공 하는 세션)에 연결 되지 않고 신뢰할 수 있는 세션의 수명 동안 동시에 또는 순차적으로 여러 전송 세션을 사용할 수 있습니다.

- 신뢰할 수 있는 세션은 SOAP 엔드포인트 간의 연결에 필요한 전송 연결 수에 관계없이 발신자 및 수신자 SOAP 엔드포인트 사이에 위치합니다. 즉, 신뢰할 수 있는 세션이 종단 간 안정성을 제공 하는 반면, TCP 안정성은 전송 연결이 끝나는 위치를 종료 합니다.

## <a name="reliable-sessions-and-bindings"></a>신뢰할 수 있는 세션 및 바인딩

앞서 설명한 것 처럼 신뢰할 수 있는 세션은 전송 중립적입니다. 또한 요청-회신 또는 이중과 같은 여러 메시지 교환 패턴에 대해 신뢰할 수 있는 세션을 설정할 수 있습니다. WCF 신뢰할 수 있는 세션은 바인딩 집합의 속성으로 노출 됩니다.

다음을 사용 하는 끝점에서 신뢰할 수 있는 세션을 사용 합니다.

- HTTP 기반 전송 표준 바인딩:

  - `WsHttpBinding` 및 요청-회신 또는 단방향 계약을 노출합니다.

  - 요청-회신 또는 간단한 단방향 서비스 계약을 통해 신뢰할 수 있는 세션을 사용 하는 경우

  - `WsDualHttpBinding` 및 이중, 요청-회신 또는 단방향 계약을 노출합니다.

  - `WsFederationHttpBinding` 및 요청-회신 또는 단방향 계약을 노출합니다.

- TCP 기반 전송 표준 바인딩:

  - `NetTcpBinding` 및 이중, 요청-회신 또는 단방향 계약을 노출합니다.

HTTPS (문제에 대 한 자세한 내용은 <a href="#reliable-sessions-and-security">신뢰할 수 있는 세션 및 보안</a>참조) 또는 명명 된 파이프 바인딩과 같은 사용자 지정 바인딩을 만들어 다른 바인딩에서 신뢰할 수 있는 세션을 사용 합니다.

서로 다른 기본 채널 형식에 대해 신뢰할 수 있는 세션을 쌓을 수 있으며, 결과적으로 신뢰할 수 있는 세션 채널 셰이프가 다릅니다. 클라이언트와 서버 모두에서 지원 되는 신뢰할 수 있는 세션 채널 형식은 사용 되는 기본 채널의 형식에 따라 달라 집니다. 다음 표에서는 기본 채널 형식의 기능으로서 클라이언트에서 지원되는 세션 채널 형식에 대해 설명합니다.

| 지원 되는 신뢰할 수 있는 세션 채널 형식&#8224; | `IRequestChannel` | `IRequestSessionChannel` | `IDuplexChannel` | `IDuplexSessionChannel` |
| ----------------------------------------------- | :---------------: | :----------------------: | :--------------: | :---------------------: |
| `IOutputSessionChannel`                         | 예               | 예                      | 예              | 예                     |
| `IRequestSessionChannel`                        | 예               | 예                      | 아니요               | 아니요                      |
| `IDuplexSessionChannel`                         | 아니요                | 아니요                       | 예              | 예                     |

&#8224;지원 되는 채널 형식은 `TChannel` 메서드에 전달 되는 제네릭 매개 변수 값에 사용할 수 있는 값입니다 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.BuildChannelFactory%60%601%28System.ServiceModel.Channels.BindingContext%29> .

다음 표에서는 기본 채널 형식의 기능으로서 서버에서 지원되는 세션 채널 형식에 대해 설명합니다.

| 지원 되는 신뢰할 수 있는 세션 채널 형식&#8225; | `IReplyChannel` | `IReplySessionChannel` | `IDuplexChannel` | `IDuplexSessionChannel` |
| ----------------------------------------------- | :-------------: | :--------------------: | :--------------: | :---------------------: |
| `IInputSessionChannel`                          | 예             | 예                    | 예              | 예                     |
| `IReplySessionChannel`                          | 예             | 예                    | 아니요               | 아니요                      |
| `IDuplexSessionChannel`                         | 아니요              | 아니요                     | 예              | 예                     |

&#8225;지원 되는 채널 형식은 `TChannel` 메서드에 전달 되는 제네릭 매개 변수 값에 사용할 수 있는 값입니다 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.BuildChannelListener%60%601%28System.ServiceModel.Channels.BindingContext%29> .

## <a name="reliable-sessions-and-security"></a>신뢰할 수 있는 세션 및 보안

통신 당사자 (서비스 및 클라이언트)가 인증 되 고 세션에서 교환 되는 메시지가 변조 되지 않도록 하려면 신뢰할 수 있는 세션의 보안을 유지 해야 합니다. 또한 신뢰할 수 있는 개별 세션의 무결성을 보장 하는 것이 중요 합니다. 신뢰할 수 있는 세션은 보안 세션 채널에서 표시 하 고 관리 하는 보안 컨텍스트에 바인딩하여 보안이 유지 됩니다. 보안 채널은 보안 세션을 제공합니다. 세션 설정 동안 교환된 보안 토큰은 신뢰할 수 있는 세션의 메시지 보안을 유지하는 데 사용됩니다.

TCP-S를 통해 신뢰할 수 있는 세션의 경우 TCP 세션은 신뢰할 수 있는 세션에 연결 됩니다. 따라서 전송 보안은 보안도 신뢰할 수 있는 세션에 연결 되도록 합니다. 이 경우 연결 재설정이 꺼집니다.

HTTPS를 사용하는 경우에만 예외입니다. SSL(Secure Sockets Layer) (SSL) 세션이 신뢰할 수 있는 세션에 바인딩되어 있지 않습니다. 보안 컨텍스트 (SSL 세션)를 공유 하는 세션은 서로 보호 되지 않으므로이로 인해 위협이 발생 합니다. 이는 응용 프로그램에 따라 실제 위협이 될 수도 있고 그렇지 않을 수도 있습니다.

## <a name="using-reliable-sessions"></a>신뢰할 수 있는 세션 사용

WCF 신뢰할 수 있는 세션을 사용 하려면 신뢰할 수 있는 세션을 지 원하는 바인딩을 사용 하 여 끝점을 만듭니다. WCF가 신뢰할 수 있는 세션을 사용 하 여 제공 하는 시스템 제공 바인딩 중 하나를 사용 하거나이를 수행 하는 사용자 지정 바인딩을 만듭니다.

기본적으로 신뢰할 수 있는 세션을 지원하고 사용하도록 설정하는 시스템 정의 바인딩은 다음과 같습니다.

- <xref:System.ServiceModel.WSDualHttpBinding>

옵션으로 신뢰할 수 있는 세션을 지 원하는 시스템 제공 바인딩은 기본적으로 다음을 포함 합니다.

- <xref:System.ServiceModel.WSHttpBinding>

- <xref:System.ServiceModel.WSFederationHttpBinding>

- <xref:System.ServiceModel.NetTcpBinding>

사용자 지정 바인딩을 만드는 방법에 대 한 예제는 [방법: HTTPS를 사용 하 여 신뢰할 수 있는 사용자 지정 세션 바인딩 만들기](how-to-create-a-custom-reliable-session-binding-with-https.md)를 참조 하세요.

신뢰할 수 있는 세션을 지 원하는 WCF 바인딩에 대 한 자세한 내용은 [시스템 제공 바인딩](../system-provided-bindings.md)을 참조 하십시오.

## <a name="when-to-use-reliable-sessions"></a>신뢰할 수 있는 세션을 사용 하는 경우

응용 프로그램에서 신뢰할 수 있는 세션을 사용 해야 하는 경우를 이해 하는 것이 중요 합니다. WCF는 동시에 활성 상태이 고 활성 상태인 끝점 간에 신뢰할 수 있는 세션을 지원 합니다. 응용 프로그램에서 기간 중 하나를 사용할 수 없는 경우에는 큐를 사용 하 여 안정성을 확보 해야 합니다.

시나리오에 TCP를 통해 연결 된 두 개의 끝점이 필요한 경우 TCP는 신뢰할 수 있는 메시지 교환을 제공할 수 있습니다. 그러나 TCP는 패킷이 한 번만 도착 하도록 보장 하기 때문에 신뢰할 수 있는 세션을 사용할 필요는 없습니다.

시나리오에 다음과 같은 특징이 있는 경우 신뢰할 수 있는 세션을 사용 하는 것이 심각 하 게 고려해 야 합니다.

- Soap 중개 (예: SOAP 라우터)

- 프록시 중개 또는 전송 브리지

- 간헐적 연결

- HTTP를 통한 세션

## <a name="see-also"></a>참고 항목

- [바인딩을 사용하여 서비스 및 클라이언트 구성](../using-bindings-to-configure-services-and-clients.md)
- [WS 신뢰할 수 있는 세션](../samples/ws-reliable-session.md)
