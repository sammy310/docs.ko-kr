---
description: '자세한 정보: 224-MessageThrottleAtSeventyPercent'
title: 224 - MessageThrottleAtSeventyPercent
ms.date: 03/30/2017
ms.assetid: 82bbbfd7-10d2-41fd-805d-2443b0c1b96b
ms.openlocfilehash: 14c08371c5db7e6f7deb0a5851a1d24dfc94475e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794275"
---
# <a name="224---messagethrottleatseventypercent"></a>224 - MessageThrottleAtSeventyPercent

## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|224|  
|키워드|EndToEndMonitoring, HealthMonitoring, 문제 해결, ServiceModel|  
|Level|경고|  
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/분석|  
  
## <a name="description"></a>설명  

 기본 서비스 스로틀 중 하나가 초과되면 `MessageThrottleExceeded` 이벤트가 내보내집니다. 작업 스파이크가 느려지고 스로틀의 현재 값이 현재 한계의 70%이면 이 이벤트가 내보내집니다. 이 이벤트는 작업이 느려지므로 한 번만 내보내집니다. 예를 들어 현재 값이 70% 표시 지점을 넘나들면(예: 70,69,70,71,70,69) 처음으로 70%가 될 때만 이 이벤트가 내보내집니다. 이 이벤트가 내보내진 후에 현재 값이 스로틀 한계를 다시 초과하면 `MessageThrottleExceeded` 이벤트가 내보내집니다.  
  
## <a name="message"></a>메시지  

 '%2'의 스로틀 제한 '%1'이(가) 70퍼센트입니다.  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|Throttle Name|`xs:string`|초과한 스로틀의 이름입니다. `MaxConcurrentCalls`, `MaxConcurrentInstances` 또는 `MaxConcurrentSessions` 중 하나입니다.|  
|제한|`xs:long`|현재 구성된 스로틀 한계입니다.|  
|HostReference|`xs:string`|웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다. 해당 형식은 ' 웹 사이트 이름 응용 프로그램 가상 경로&#124;서비스 가상 경로&#124;ServiceName '으로 정의 됩니다. 예: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.|  
|AppDomain|`xs:string`|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
