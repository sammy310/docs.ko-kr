---
title: Wcf 바인딩 및 전송-WCF 개발자를 위한 gRPC
description: 다양 한 WCF 바인딩 및 전송에서 gRPC와 비교 하는 방법에 대해 알아봅니다.
ms.date: 12/15/2020
ms.openlocfilehash: 7a50e3e4468d86a6140066502a765818119642d4
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938509"
---
# <a name="wcf-bindings-and-transports"></a>WCF 바인딩 및 전송

WCF (Windows Communication Foundation)에는 서로 다른 네트워크 프로토콜, 통신 형식 및 기타 구현 세부 정보를 지정 하는 기본 제공 *바인딩이* 있습니다. gRPC는 네트워크 프로토콜과 통신 형식이 하나씩만 효과적입니다. 기술적으로는 통신 형식을 사용자 지정할 *수* 있지만이는이 책의 범위를 벗어나는 것입니다. 대부분의 경우 gRPC가 최상의 솔루션을 제공 한다는 것을 알게 될 것입니다.

다음은 가장 관련성이 높은 WCF 바인딩과 이러한 바인딩이 gRPC의 해당 바인딩과 비교 되는 방법에 대 한 간단한 설명입니다.

## <a name="nettcp"></a>Wcf-nettcp

WCF의 NetTCP 바인딩은 영구 연결, 작은 메시지 및 양방향 메시징을 허용 합니다. 그러나 .NET 클라이언트와 서버 간에만 작동 합니다. gRPC는 동일한 기능을 허용 하지만 여러 프로그래밍 언어 및 플랫폼에서 지원 됩니다.

gRPC는 WCF의 NetTCP 바인딩의 많은 기능을 포함 하지만 항상 동일한 방식으로 구현 되지는 않습니다. 예를 들어 WCF에서 암호화는 구성을 통해 제어 되 고 프레임 워크에서 처리 됩니다. GRPC에서는 TLS를 통한 HTTP/2를 통해 연결 수준에서 암호화가 이루어집니다.

## <a name="http"></a>HTTP

BasicHttpBinding 이라는 WCF 바인딩은 일반적으로 텍스트를 기반으로 하며 SOAP를 통신 형식으로 사용 합니다. NetTCP 바인딩에 비해 속도가 느립니다. 플랫폼 간 상호 운용성 또는 인터넷 인프라를 통한 연결을 제공 하는 데 사용 됩니다.

GRPC의 동급는 메시지에 대 한 이진 Protobuf 통신 형식의 기본 전송 계층으로 HTTP/2를 사용 합니다. 따라서 최신 프로그래밍 언어 및 프레임 워크를 사용 하 여 NetTCP 서비스 수준에서 성능을 제공 하 고 전체 플랫폼 간 상호 운용성을 제공할 수 있습니다.

## <a name="named-pipes"></a>명명된 파이프

WCF는 동일한 물리적 컴퓨터의 프로세스 간 통신을 위해 *명명 된 파이프* 바인딩을 제공 했습니다. ASP.NET Core gRPC의 첫 번째 릴리스는 명명 된 파이프를 지원 하지 않습니다. 명명 된 파이프에 대 한 클라이언트 및 서버 지원 추가 (및 Unix 도메인 소켓)는 향후 릴리스에 대 한 목표입니다.

## <a name="msmq"></a>MSMQ

MSMQ는 독점 Windows 메시지 큐입니다. WCF에 대 한 WCF의 바인딩을 사용 하면 나중에 언제 든 지 처리 될 수 있는 클라이언트에서 "발생 하 고 잊어버린" 요청을 처리할 수 있습니다. gRPC는 기본적으로 메시지 큐 기능을 제공 하지 않습니다.

가장 좋은 대안은 Azure Service Bus, RabbitMQ 또는 Kafka과 같은 메시징 시스템을 직접 사용 하는 것입니다. 메시지를 큐에 직접 배치 하는 클라이언트 또는 메시지를 큐 하는 gRPC 클라이언트 스트리밍 서비스를 사용 하 여이 기능을 구현할 수 있습니다.

## <a name="webhttpbinding"></a>WebHttpBinding

및 특성을 사용 하는 WebHttpBinding (WCF REST 라고도 함)를 `WebGet` `WebInvoke` 사용 하면이 동작이 일반적이 지 않은 경우에 JSON을 사용 하 여 RESTful api를 개발할 수 있습니다. WCF REST를 사용 하 여 빌드된 RESTful API를 사용 하는 경우 일반적인 ASP.NET Core MVC Web API 응용 프로그램으로 마이그레이션하는 것이 좋습니다. 이 마이그레이션은 gRPC로의 변환과 동일한 기능을 제공 합니다.

>[!div class="step-by-step"]
>[이전](wcf-endpoints-grpc-methods.md)
>[다음](rpc-types.md)
