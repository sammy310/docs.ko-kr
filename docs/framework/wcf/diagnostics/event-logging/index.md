---
title: WCF에서 이벤트 로깅
ms.date: 03/30/2017
helpviewer_keywords:
- event logging [WCF]
ms.assetid: aac0530d-f44c-45a1-bada-e30e0677b41f
ms.openlocfilehash: adff5bf2fad9f78fccbb606a5bd27f2f1dc32647
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64638760"
---
# <a name="event-logging-in-wcf"></a>WCF에서 이벤트 로깅
Windows Communication Foundation (WCF)는 Windows 이벤트 로그에는 내부 이벤트를 추적합니다.  
  
## <a name="viewing-event-logs"></a>이벤트 로그 보기  
 이벤트 로깅은 기본적으로 활성화되며 비활성화 메커니즘이 없습니다. 이벤트 뷰어를 사용 하 여 WCF에 의해 기록 된 이벤트를 볼 수 있습니다. 이 도구를 실행 하려면 클릭 **시작**, 클릭 **제어판**를 두 번 클릭 **관리 도구**를 차례로 클릭 한 다음 **이벤트 뷰어**.  
  
### <a name="application-event-log"></a>응용 프로그램 이벤트 로그  
 합니다 **응용 프로그램 이벤트 로그** WCF에 의해 생성 된 이벤트의 대부분을 포함 합니다. 대부분의 항목은 응용 프로그램에서 특정 기능을 시작하지 못한 것을 나타냅니다. 다음과 같은 경우를 예로 들 수 있습니다.  
  
- 메시지 로깅/추적: WCF 추적 및 메시지 로깅 실패 하면 이벤트 로그에 이벤트를 씁니다. 그러나 모든 추적 실패가 이벤트를 트리거하는 것은 아닙니다. 이벤트 로그가 추적 오류로 가득 차을 방지 하려면 WCF는 이러한 이벤트에 대 일 분 블랙 아웃 기간을 구현 합니다. 이 이벤트 로그에 추적 실패를 기록 하는 WCF, 하는 경우 수행 되지 않습니다 다시 10 분 이상에 대 한 것을 의미 합니다.  
  
- 공유 수신기: WCF TCP Port Sharing Service를 시작 하는 데 실패할 경우 이벤트를 기록 합니다.  
  
- [!INCLUDE[infocard](../../../../../includes/infocard-md.md)]: 서비스가 시작 되지 않을 때 이벤트를 기록 합니다.  
  
- 시작 실패 또는 크래시 등의 위험 및 오류 이벤트  
  
- 메시지 로깅 켜 짐: 메시지 로깅이 설정 되 면 이벤트를 기록 합니다. 이는 관리자에게 중요한 응용 프로그램 관련 정보가 메시지 헤더 및 본문에 기록될 수 있다는 것을 알리기 위해서입니다.  
  
- `enableLoggingKnownPII` 파일의 `machineSettings` 요소에서 `machine.config` 특성이 설정되면 이벤트가 기록됩니다. 이 특성에서는 시스템에서 실행 중인 응용 프로그램 중 알려진 PII(개인적으로 식별할 수 있는 정보)의 로그가 허용되는 것이 있는지 여부를 지정합니다.  
  
- 특정 응용 프로그램에 대해 `logKnownPii` 또는 `app.config` 파일에서 `web.config` 특성이 PII 로깅을 켜도록 `true`로 설정되어 있지만 `enableLoggingKnownPII` 파일의 `machineSettings` 요소에 있는 `machine.config` 특성이 `false`로 설정되어 있으면 이벤트가 기록됩니다. 또한 `logKnownPii` 및 `enableLoggingKnownPII`가 모두 `true`로 설정되어 있으면 이벤트가 기록됩니다. 이러한 구성 설정에 대 한 자세한 내용은 보안 섹션을 참조 합니다 [메시지 로깅 구성](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) 항목입니다.  
  
### <a name="security-event-log"></a>보안 이벤트 로그  
 합니다 **보안 이벤트 로그** WCF에서 기록 하는 보안 감사 이벤트가 포함 됩니다.  
  
### <a name="system-event-log"></a>시스템 이벤트 로그  
 WCF를 기록 하지 않습니다 모든 항목는 **시스템 이벤트 로그**합니다.  
  
### <a name="event-log-entries"></a>이벤트 로그 항목  
 합니다 **원본** 이벤트의 로그 항목을 생성 하는 어셈블리의 이름입니다.  
  
 이벤트 로그 항목의 형식은 이벤트의 심각도를 나타내는 데 사용됩니다. 각 이벤트는 응용 프로그램에서 이벤트를 보고할 때 나타내는 단일 형식이어야 합니다. 이벤트 뷰어는 이 형식을 사용하여 로그의 목록 보기에 표시할 아이콘을 결정합니다. 이벤트 로그 항목의 다른 이벤트 형식은 <xref:System.Diagnostics.EventLogEntryType>을 참조하십시오.  
  
 "자세한 정보"를 클릭 하면 이벤트 뷰어에서 이벤트를 볼 때 이벤트 뷰어에서 인터넷을 통해 정보를 보낼 수 있습니다. 자세한 내용은 이벤트 뷰어 도움말을 참조하십시오.  
  
## <a name="see-also"></a>참고자료

- [관리 및 진단](../../../../../docs/framework/wcf/diagnostics/index.md)
- [이벤트 일반 참조](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
