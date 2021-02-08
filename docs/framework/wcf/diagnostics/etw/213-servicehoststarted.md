---
description: '자세한 정보: 213-ServiceHostStarted'
title: 213 - ServiceHostStarted
ms.date: 03/30/2017
ms.assetid: a6f7facc-342f-46bb-9d52-a470178ba6bb
ms.openlocfilehash: 5e2b5b7c633ef053c449ad62c4f8fee40798a386
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794418"
---
# <a name="213---servicehoststarted"></a>213 - ServiceHostStarted

## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|213|  
|키워드|EndToEndMonitoring, HealthMonitoring, 문제 해결, ServiceHost|  
|Level|LogAlways|  
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/분석|  
  
## <a name="description"></a>설명  

 이 이벤트는 웹 호스팅 호스트가 시작될 때 내보내집니다. 일반적으로 이러한 경우는 서비스가 메시지에 의해 활성화될 때 발생하며, 서비스가 자동으로 시작되도록 구성된 경우에도 발생할 수 있습니다.  
  
## <a name="message"></a>메시지  

 ServiceHost 시작: '%1'.  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|Service Type Name|`xs:string`|서비스 구현 형식의 CLR FullName입니다.|  
|HostReference|`xs:string`|웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다. 해당 형식은 ' 웹 사이트 이름 응용 프로그램 가상 경로&#124;서비스 가상 경로&#124;ServiceName '으로 정의 됩니다. 예: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.|  
|AppDomain|`xs:string`|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
