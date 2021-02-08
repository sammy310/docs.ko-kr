---
description: '자세한 정보: ETW를 사용한 분석 추적'
title: ETW를 사용한 분석 추적
ms.date: 03/30/2017
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
ms.openlocfilehash: fd40d40de2508fd251c793e4455c1e656a1cbbf6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99798799"
---
# <a name="analytic-tracing-with-etw"></a>ETW를 사용한 분석 추적

WCF (Windows Communication Foundation) 분석 추적은 WCF 서비스를 실행 하는 동안 진단 정보를 캡처하는 방법을 제공 합니다. Wcf 분석 추적 이벤트는 프로덕션 환경에서 wcf 서비스의 문제를 해결할 수 있도록 WCF 스택의 주요 지점에서 내보내집니다. WCF 서비스에 대 한 분석 추적은 wcf 서비스를 호스팅하는 제품 서버의 성능에 최소한의 영향을 미칩니다 [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] . 이러한 이벤트는 ETW (ETW(Windows용 이벤트 추적)) 세션으로 매우 효율적으로 내보내집니다.  
  
## <a name="in-this-section"></a>섹션 내용  

 [분석 추적 개요](analytic-tracing-overview.md)  
 에서 WCF 분석 추적이 작동 하는 방식에 대해 설명 [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] 합니다.  
  
 [동적으로 분석 추적을 사용하도록 설정](dynamically-enabling-analytic-tracing.md)  
 ETW를 사용하여 추적을 동적으로 사용하거나 사용하지 않도록 설정하는 방법에 대해 설명합니다.  
  
 [메시지 흐름 추적 구성](configuring-message-flow-tracing.md)  
 메시지 흐름 추적을 구성하는 방법에 대해 설명합니다.  
  
 [분석 추적 이벤트 참조](analytic-trace-event-reference.md)  
 이벤트 ID와 함께 해당 이벤트 수준, 이벤트 메시지 및 키워드가 포함된 표를 보여 줍니다.  
  
## <a name="see-also"></a>참고 항목

- [Windows용 WCF 서비스 및 이벤트 추척](../../samples/wcf-services-and-event-tracing-for-windows.md)
- [Windows에서 이벤트 추적으로 이벤트 추적](../../../windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
