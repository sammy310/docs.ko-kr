---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.date: 03/30/2017
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
ms.openlocfilehash: e80fecf508158dcb53f08b75c8f9486c13e403a4
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674792"
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a>System.ServiceModel.Channels.MsmqMessageDropped
MSMQ에서 메시지를 삭제했습니다.  
  
## <a name="description"></a>Description  
 추적은 MSMQ 메시지가 삭제되었음을 나타냅니다. Windows 통신 재단(WCF)(NetMsmqBinding 또는 MsmqIntegrationBinding과 함께 사용)이 처리할 수 없는 경우 MSMQ 메시지를 삭제할 수 있습니다. 이러한 메시지를 포이즌 메시지라고 합니다.  
  
 포이즌 메시지는 NetMsmqBinding 또는 MsmqIntegrationBinding의 `ReceiveErrorHandling` 속성을 `Drop`으로 설정할 경우 삭제됩니다. 삭제된 메시지는 큐에서 제거되고 더 이상 복구될 수 없습니다.  
  
 메시지가 독이 되는 시기와 메시지를 적절하게 처리하도록 서비스를 구성하는 방법에 대한 자세한 내용은 [독 메시지 처리를](../../feature-details/poison-message-handling.md)참조하십시오.  
  
## <a name="see-also"></a>참고 항목

- [추적](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [추적을 사용하여 애플리케이션 문제 해결](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [관리 및 진단](../../../../../docs/framework/wcf/diagnostics/index.md)
- [포이즌 메시지 처리](../../feature-details/poison-message-handling.md)
