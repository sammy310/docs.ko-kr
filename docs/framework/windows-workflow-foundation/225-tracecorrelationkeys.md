---
description: '자세한 정보: 225-TraceCorrelationKeys'
title: 225 - TraceCorrelationKeys
ms.date: 03/30/2017
ms.assetid: d9083aaf-3816-4c1c-bae0-2d7f49628345
ms.openlocfilehash: c5fdb9305815cdc4df6bbae3e54209d2b5cffd9d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99778115"
---
# <a name="225---tracecorrelationkeys"></a>225 - TraceCorrelationKeys

## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|225|  
|키워드|문제 해결, ServiceModel|  
|Level|정보|  
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/분석|  
  
## <a name="description"></a>설명  

 이 이벤트는 워크플로 서비스에 내용 기반 상관 관계가 사용될 때 내보내집니다. 여기에는 메시지를 인스턴스에 연결하기 위해 적용되는 상관 관계 키가 포함됩니다.  
  
## <a name="message"></a>메시지  

 '%3' 부모 범위에서 '%2' 값을 사용하여 '%1' 상관 관계 키를 계산했습니다.  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|Instance Key|`xs:GUID`|상관 관계 값에서 생성된 키입니다.|  
|값|`xs:string`|상관 관계 인스턴스 키를 컴퓨팅하는 데 사용된 값입니다.|  
|Parent Scope|`xs:string`||  
|HostReference|`xs:string`|웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다. 해당 형식은 ' 웹 사이트 이름 응용 프로그램 가상 경로&#124;서비스 가상 경로&#124;ServiceName '으로 정의 됩니다. 예: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.|  
|AppDomain|`xs:string`|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
