---
description: '자세한 정보: 신뢰할 수 있는 세션에 대 한 모범 사례'
title: 신뢰할 수 있는 세션을 위한 최선의 방법
ms.date: 03/30/2017
ms.assetid: b94f6e01-8070-40b6-aac7-a2cb7b4cb4f2
ms.openlocfilehash: 4b05dd914d2c5b8ec7941417b727bec1e5b43ba4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99643672"
---
# <a name="best-practices-for-reliable-sessions"></a>신뢰할 수 있는 세션을 위한 최선의 방법

이 항목에서는 신뢰할 수 있는 세션에 대 한 모범 사례를 설명 합니다.

## <a name="setting-maxtransferwindowsize"></a>MaxTransferWindowSize 설정

WCF (Windows Communication Foundation)의 신뢰할 수 있는 세션은 전송 창을 사용 하 여 클라이언트 및 서비스에서 메시지를 보관 합니다. 구성 가능한 속성 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxTransferWindowSize%2A>는 전송 창이 보관할 수 있는 메시지 수를 나타냅니다.

보낸 사람에서이는 전송 창이 승인을 기다리는 동안 보관할 수 있는 메시지 수를 나타냅니다. 수신기에서 서비스에 대해 버퍼링 할 메시지 수를 나타냅니다.

적절 한 크기를 선택 하면 네트워크의 효율성과 서비스의 최적 용량에 영향을 줍니다. 다음 섹션에서는이 속성의 값과 값의 영향을 선택할 때 고려해 야 할 사항에 대해 자세히 설명 합니다.

기본 전송 창 크기는 8 개 메시지입니다.

### <a name="efficient-use-of-the-network"></a>네트워크의 효율적인 사용

이 컨텍스트에서 *네트워크* 라는 용어는 클라이언트 (발신자)와 서비스 (수신자) 간의 통신 기반으로 사용 되는 모든 항목에 해당 합니다. 여기에는 SOAP 라우터 또는 HTTP 프록시/방화벽을 포함 하 여 간의 전송 연결 및 중간 또는 브리지가 포함 됩니다.

네트워크를 효율적으로 사용하려면 네트워크 용량을 최대한 사용합니다. 네트워크를 통해 초당 전송할 수 있는 데이터 양 (*데이터 요금*) 및 발신자에서 받는 사람으로 데이터를 전송 하는 데 걸리는 시간 (*대기 시간*)은 네트워크를 효과적으로 활용 하는 방식에 영향을 줍니다.

발신자의 경우 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxTransferWindowSize%2A> 속성은 전송 창이 승인을 기다리는 동안 보관할 수 있는 메시지 수를 나타냅니다. 네트워크 대기 시간이 높고 응답성이 뛰어나고 효과적인 네트워크 사용률을 보장 하기 위해 전송 창 크기를 늘려야 합니다.

예를 들어 발신자가 데이터 속도를 유지 하는 경우에도 발신자와 수신자 사이에 몇 개의 중개자가 있거나 데이터가 손실 된 매개 또는 네트워크를 통해 전달 되어야 하는 경우 대기 시간이 길어질 수 있습니다. 따라서 발신자는 네트워크에서 보낼 새 메시지를 수락 하기 전에 전송 창에서 메시지에 대 한 승인을 기다려야 합니다. 대기 시간이 긴 버퍼가 작을수록 네트워크 사용률은 줄어듭니다. 반면, 서비스가 클라이언트에서 보낸 데이터의 최고 속도를 파악 해야 할 수 있으므로 전송 창 크기가 너무 높으면 서비스에 영향을 줄 수 있습니다.

### <a name="running-the-service-to-capacity"></a>용량에 서비스 실행

네트워크를 효율적으로 사용 하는 경우에도 최적의 용량에서 서비스를 실행 하는 것이 좋습니다. 수신자의 전송 창 크기 속성은 수신자가 버퍼링할 수 있는 메시지 수를 나타냅니다. 이 메시지 버퍼링은 네트워크 흐름 제어에 도움을 줄 뿐만 아니라 서비스를 최대 용량으로 실행할 수 있도록 합니다. 예를 들어 버퍼가 메시지 하나이 고 메시지가 서비스에서 처리할 수 있는 것 보다 빠르게 도착할 경우 네트워크에서 메시지를 삭제 하 고 용량이 낭비 되거나 사용률이 낮은 것일 수 있습니다.

버퍼를 사용 하면 이전에 받은 메시지를 처리 하는 동안 동시에 메시지를 받고 버퍼링 하므로 서비스 가용성이 향상 됩니다.

`MaxTransferWindowSize`발신자와 수신자 모두에 대해 동일한를 사용 하는 것이 좋습니다.

### <a name="enabling-flow-control"></a>흐름 제어 사용

*흐름 제어* 는 발신자와 수신자가 서로 속도를 유지 하도록 보장 하는 메커니즘입니다. 즉, 메시지를 사용 하 고 생성 되는 속도에 따라 처리 합니다. 클라이언트 및 서비스의 전송 창 크기는 발신자와 수신자가 적절한 동기화 창 내에 있도록 합니다.

<xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled%2A> `true` Wcf 클라이언트와 wcf 서비스 간에 신뢰할 수 있는 세션을 사용 하는 경우 속성을로 설정 하는 것이 좋습니다.

## <a name="setting-maxpendingchannels"></a>MaxPendingChannels 설정

서로 다른 클라이언트에서 신뢰할 수 있는 세션 통신을 가능 하 게 하는 서비스를 작성할 때 많은 클라이언트에서 동시에 서비스에 대 한 신뢰할 수 있는 세션을 설정할 수 있습니다. 이 경우 서비스 응답은 `MaxPendingChannels` 속성에 따라 달라집니다.

발신자가 수신자에 대해 신뢰할 수 있는 세션 채널을 만드는 경우 발신자와 수신자 간의 핸드셰이크에서 신뢰할 수 있는 세션이 설정됩니다. 신뢰할 수 있는 세션이 설정된 후 채널은 서비스에서 허용할 수 있도록 보류 중인 채널 큐에 저장됩니다. `MaxPendingChannels` 속성은 이 상태에 있을 수 있는 채널 수를 나타냅니다.

서비스가 더 이상 채널을 허용할 수 없는 상태에 있을 수 있습니다. 큐가 가득 찬 경우에는 신뢰할 수 있는 세션을 설정 하는 시도가 거부 되며 클라이언트는 다시 시도해 야 합니다.

큐의 보류 중인 채널이 긴 기간 동안 큐에 남아 있을 수도 있습니다. 그 동안에는 신뢰할 수 있는 세션에 대 한 비활성 시간 제한이 발생 하 여 채널이 오류가 발생 한 상태로 전환 될 수 있습니다.

여러 클라이언트를 동시에 서비스 하는 서비스를 작성 하는 경우 요구 사항에 적합 한 값을 설정 해야 합니다. 속성 값을 너무 높게 설정 하면 `MaxPendingChannels` 작업 집합에 영향을 줍니다.

의 기본값은 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxPendingChannels%2A> 4 개의 채널입니다.

## <a name="reliable-sessions-and-hosting"></a>신뢰할 수 있는 세션 및 호스팅

웹에서 신뢰할 수 있는 세션을 사용 하는 서비스를 호스팅하는 경우 다음과 같은 중요 한 사항을 고려해 야 합니다.

- 신뢰할 수 있는 세션은 상태 저장 세션이며 상태는 AppDomain에 유지됩니다. 따라서 신뢰할 수 있는 세션의 일부인 모든 메시지는 동일한 AppDomain에서 처리되어야 합니다. 팜 또는 정원의 크기가 한 노드 보다 큰 웹 팜 및 웹 가든은이 제약 조건을 보장할 수 없습니다.

- 이중 HTTP 채널을 사용 하는 신뢰할 수 있는 세션 (예:를 사용 하는 경우 `WsDualHttpBinding` )은 클라이언트 당 두 HTTP 연결의 기본값 보다 더 많은 요구를 요구 합니다. 즉, 동시 응용 프로그램 및 프로토콜 메시지가 지정 된 시간에 매번 전송 될 수 있으므로 신뢰할 수 있는 이중 세션에는 각 방법으로 최대 2 개의 연결이 필요할 수 있습니다. 서비스의 메시지 교환 패턴에 따라 특정 조건에서 이중 HTTP 및 신뢰할 수 있는 세션을 사용 하 여 웹 호스팅 서비스의 교착 상태를 발생 시킬 수 있음을 의미 합니다. 클라이언트 별로 허용 되는 HTTP 연결 수를 늘리려면 관련 구성 파일에 다음을 추가 합니다 (예: 해당 서비스의 *web.config* ).

  ```xml
  <configuration>
    <system.net>
      <connectionManagement>
        <add name="*" maxconnection="4" />
      </connectionManagement>
    </system.net>
  </configuration>
  ```

  특성의 값은 `maxconnection` 필요한 연결 수입니다. 이 경우 최소는 네 개의 연결 이어야 합니다.
