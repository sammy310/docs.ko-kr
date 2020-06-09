---
title: System.ServiceModel.MessageProcessingPaused
ms.date: 03/30/2017
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
ms.openlocfilehash: 85bec8255e0d20d6e76ea354e5b8c42b83d7d8e6
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598153"
---
# <a name="systemservicemodelmessageprocessingpaused"></a>System.ServiceModel.MessageProcessingPaused
System.ServiceModel.MessageProcessingPaused  
  
## <a name="description"></a>Description  
 메시지를 처리하는 동안 스레드가 전환되었습니다.  
  
 메시지 처리는 다음 이유로 인해 일시 중지될 수 있습니다.  
  
- ConcurrencyMode가 단일하거나 재진입할 수 있으며, 서비스가 다른 메시지를 처리하고 있습니다.  
  
- 트랜잭션이 사용하도록 설정되어 있으며, 서비스가 다른 트랜잭션을 처리하고 있습니다.  
  
- 현재 동기화 컨텍스트가 아닙니다.  
  
## <a name="see-also"></a>참고 항목

- [추적](index.md)
- [추적을 사용하여 애플리케이션 문제 해결](using-tracing-to-troubleshoot-your-application.md)
- [관리 및 진단](../index.md)
