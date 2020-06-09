---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.date: 03/30/2017
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
ms.openlocfilehash: 4b016f53a75d9527a5cd1bbadacacd650b7f35b0
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601917"
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a>System.ServiceModel.Channels.MsmqMessageDropped
MSMQ에서 메시지를 삭제했습니다.  
  
## <a name="description"></a>Description  
 추적은 MSMQ 메시지가 삭제되었음을 나타냅니다. Windows Communication Foundation (WCF) (NetMsmqBinding 또는 MsmqIntegrationBinding에서 사용)가 처리할 수 없는 경우 MSMQ 메시지를 삭제할 수 있습니다. 이러한 메시지를 포이즌 메시지라고 합니다.  
  
 포이즌 메시지는 NetMsmqBinding 또는 MsmqIntegrationBinding의 `ReceiveErrorHandling` 속성을 `Drop`으로 설정할 경우 삭제됩니다. 삭제된 메시지는 큐에서 제거되고 더 이상 복구될 수 없습니다.  
  
 메시지가 포이즌 메시지를 처리 하 고 적절 하 게 처리 하도록 서비스를 구성 하는 방법에 대 한 자세한 내용은 [포이즌 메시지 처리](../../feature-details/poison-message-handling.md)를 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- [추적](index.md)
- [추적을 사용하여 애플리케이션 문제 해결](using-tracing-to-troubleshoot-your-application.md)
- [관리 및 진단](../index.md)
- [포이즌 메시지 처리](../../feature-details/poison-message-handling.md)
