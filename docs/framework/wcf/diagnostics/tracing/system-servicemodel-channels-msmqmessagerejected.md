---
title: System.ServiceModel.Channels.MsmqMessageRejected
ms.date: 03/30/2017
ms.assetid: 9b7c10a7-2af6-44a2-8b1a-90bba0c7cf26
ms.openlocfilehash: 8f783dcd4b966ed89c24d724918a3923c5a2d0b1
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674766"
---
# <a name="systemservicemodelchannelsmsmqmessagerejected"></a>System.ServiceModel.Channels.MsmqMessageRejected
MSMQ에서 메시지를 거부했습니다.  
  
## <a name="description"></a>Description  
 이 추적은 MSMQ 메시지가 거부되었음을 나타냅니다.  
  
 MsMQ 메시지는 Windows 통신 재단(NetMsmqBinding 또는 MsmqIntegrationBinding)과 함께 사용)이 이를 처리할 수 없는 경우 거부될 수 있습니다. 이러한 메시지를 포이즌 메시지라고 합니다. 포이즌 메시지는 NetMsmqBinding 또는 MsmqIntegrationBinding의 `ReceiveErrorHandling` 속성을 `Reject`로 설정할 경우 거부됩니다. 거부된 메시지는 보낸 사람의 [배달 못한 편지 대기열로](https://docs.microsoft.com/dotnet/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures)다시 배달됩니다.  
  
 메시지가 독이 되는 시기와 메시지를 적절하게 처리하도록 서비스를 구성하는 방법에 대한 자세한 내용은 [독 메시지 처리를](../../feature-details/poison-message-handling.md)참조하십시오.  
  
 MSMQ에서 거부된 메시지의 의미에 대한 자세한 내용은 [MQMarkMessage거부를](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))참조하십시오.  
  
## <a name="see-also"></a>참고 항목

- [추적](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [추적을 사용하여 애플리케이션 문제 해결](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [관리 및 진단](../../../../../docs/framework/wcf/diagnostics/index.md)
- [포이즌 메시지 처리](../../feature-details/poison-message-handling.md)
- [MQMark메시지거부](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))
