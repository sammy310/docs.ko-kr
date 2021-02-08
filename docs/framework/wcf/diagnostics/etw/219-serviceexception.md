---
description: '자세한 정보: 219-ServiceException'
title: 219 - ServiceException
ms.date: 03/30/2017
ms.assetid: 81e2efac-39aa-4ed2-85a9-97eb8793b844
ms.openlocfilehash: b2ac12d6c5c68517b085b39dd7d0f81c39db9ebd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794327"
---
# <a name="219---serviceexception"></a>219 - ServiceException

## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|219|  
|키워드|EndToEndMonitoring, HealthMonitoring, 문제 해결, ServiceModel|  
|Level|Error|  
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/분석|  
  
## <a name="description"></a>설명  

 이 이벤트는 WCF 서비스에서 처리되지 않은 예외가 발생할 때 내보내집니다. 이러한 처리되지 않은 예외로는 활성화 중에 발생한 예외, 메시지 처리 중에 발생한 예외 및 사용자 코드에서 발생한 예외가 있습니다.  
  
## <a name="message"></a>메시지  

 메시지를 처리하는 동안 '%2' 형식의 처리되지 않은 예외가 발생했습니다. 전체 예외 ToString: %1.  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|ExceptionToString|`xs:string`|CLR 예외에 대해 `ToString`()을 호출한 결과입니다.|  
|ExceptionTypeName|`xs:string`|예외 형식의 CLR FullName입니다.|  
|HostReference|`xs:string`|웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다. 해당 형식은 ' 웹 사이트 이름 응용 프로그램 가상 경로&#124;서비스 가상 경로&#124;ServiceName '으로 정의 됩니다. 예: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.|  
|AppDomain|`xs:string`|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
