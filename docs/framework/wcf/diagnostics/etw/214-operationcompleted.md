---
description: '자세한 정보: 214-OperationCompleted'
title: 214 - OperationCompleted
ms.date: 03/30/2017
ms.assetid: a6287eef-023f-4816-813c-1802c82366df
ms.openlocfilehash: aad1ac49667a2ebbf172b5132507584e05d0f03e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794392"
---
# <a name="214---operationcompleted"></a>214 - OperationCompleted

## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|214|  
|키워드|HealthMonitoring, EndToEndMonitoring, 문제 해결, ServiceModel|  
|Level|정보|  
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/분석|  
  
## <a name="description"></a>설명  

 이 이벤트는 서비스 모델의 기본 `OperationInvoker`가 메서드에서 예외를 throw하지 않고 메서드에 대한 호출을 완료하면 내보내집니다.  
  
## <a name="message"></a>메시지  

 OperationInvoker가 '%1' 메서드에 대한 호출을 완료했습니다. 메서드 호출 기간은 '%2'밀리초입니다.  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|메서드 이름|`xs:string`|`OperationInvoker`의 호출을 받은 메서드의 CLR 이름입니다.|  
|Duration|`xs:long`|`OperationInvoker`가 메서드를 호출하는 데 걸린 시간(밀리초)입니다.|  
|HostReference|`xs:string`|웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다. 해당 형식은 ' 웹 사이트 이름 응용 프로그램 가상 경로&#124;서비스 가상 경로&#124;ServiceName '으로 정의 됩니다. 예: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.|  
|AppDomain|`xs:string`|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
