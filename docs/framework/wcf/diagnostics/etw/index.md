---
title: ETW를 사용한 분석 추적
ms.date: 03/30/2017
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
ms.openlocfilehash: cff13439995d8a90da15b7afa15723f21574e35e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61962047"
---
# <a name="analytic-tracing-with-etw"></a>ETW를 사용한 분석 추적
Windows Communication Foundation (WCF) 분석 추적에는 WCF 서비스를 실행 하는 동안 진단 정보를 캡처할 수가 있습니다. 프로덕션 환경에서 WCF 서비스의 문제를 해결할 수 WCF 스택의 주요 지점에서 WCF 분석 추적 이벤트를 내보냅니다. WCF 서비스에 대 한 분석 추적에 미치는 영향을 최소화 프로덕션 서버의 성능에 호스팅하는 [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] WCF 서비스 처럼 이러한 이벤트에 대 한 Windows ETW (이벤트 추적) 세션에 매우 효율적으로 내보내집니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [분석 추적 개요](../../../../../docs/framework/wcf/diagnostics/etw/analytic-tracing-overview.md)  
 WCF 분석 추적에서 작동 하는 방법에 대해 설명 [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)]합니다.  
  
 [동적으로 분석 추적을 사용하도록 설정](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md)  
 ETW를 사용하여 추적을 동적으로 사용하거나 사용하지 않도록 설정하는 방법에 대해 설명합니다.  
  
 [메시지 흐름 추적 구성](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md)  
 메시지 흐름 추적을 구성하는 방법에 대해 설명합니다.  
  
 [분석 추적 이벤트 참조](../../../../../docs/framework/wcf/diagnostics/etw/analytic-trace-event-reference.md)  
 이벤트 ID와 함께 해당 이벤트 수준, 이벤트 메시지 및 키워드가 포함된 표를 보여 줍니다.  
  
## <a name="see-also"></a>참고자료

- [WCF 서비스 및 Windows용 이벤트 추적](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)
- [Windows에서 이벤트 추적으로 이벤트 추적](../../../../../docs/framework/windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
