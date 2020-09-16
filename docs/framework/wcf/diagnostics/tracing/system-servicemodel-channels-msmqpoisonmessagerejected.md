---
title: System.ServiceModel.Channels.MsmqPoisonMessageRejected
ms.date: 03/30/2017
ms.assetid: 0e64b9bd-1f12-43df-a189-d7be3c2bace1
ms.openlocfilehash: c5401bae1d8e7f61939d8de321353f59f412f966
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90535335"
---
# <a name="systemservicemodelchannelsmsmqpoisonmessagerejected"></a>System.ServiceModel.Channels.MsmqPoisonMessageRejected
포이즌 메시지가 거부되었습니다.  
  
## <a name="description"></a>Description  

 이 추적은 포이즌 메시지가 발생되어 거부되었음을 나타냅니다. 이는 NetMsmqBinding 또는 MsmqIntegrationBinding의 `ReceiveErrorHandling` 속성을 `Reject`로 설정할 경우 발생합니다. 거부 된 메시지는 보낸 사람의 [배달 못 한 편지 큐](../../feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md)로 다시 배달 됩니다.  
  
 메시지가 포이즌 메시지를 처리 하 고 적절 하 게 처리 하도록 서비스를 구성 하는 방법에 대 한 자세한 내용은 [포이즌 메시지 처리](../../feature-details/poison-message-handling.md)를 참조 하세요. MSMQ에서 거부 된 메시지의 의미에 대 한 자세한 내용은 [Mqmarkmessagerejected](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85))않음을 참조 하세요.  
  
## <a name="see-also"></a>참조

- [추적](index.md)
- [추적을 사용하여 애플리케이션 문제 해결](using-tracing-to-troubleshoot-your-application.md)
- [관리 및 진단](../index.md)
- [포이즌 메시지 처리](../../feature-details/poison-message-handling.md)
- [MQMarkMessageRejected](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85))
