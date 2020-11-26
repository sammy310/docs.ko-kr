---
title: 302 - UserDefinedWarningOccurred
ms.date: 03/30/2017
ms.assetid: 8d1f0bf1-0151-45e6-be92-573d397b54de
ms.openlocfilehash: b942b2e9716713371b8679fc9df9b9634dfc7283
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96243445"
---
# <a name="302---userdefinedwarningoccurred"></a>302 - UserDefinedWarningOccurred

## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|302|  
|키워드|문제 해결, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring|  
|Level|경고|  
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/분석|  
  
## <a name="description"></a>Description  

 이 이벤트는 사용자 코드에서 내보내집니다. 개발자는 자신의 서비스에서 사용자 정의 경고 이벤트가 발생할 때 이 이벤트를 내보낼 수 있습니다. 이 작업은 <xref:System.Diagnostics.Eventing> API를 사용하여 수행할 수 있습니다. 이외에도 이 API를 래핑하고 이 이벤트를 적절히 내보내는 방법을 보여 주는 WCF 샘플을 사용할 수도 있습니다.  
  
## <a name="message"></a>메시지  

 이름:'%1', 참조:'%2', 페이로드:%3  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|Description|  
|--------------------|--------------------|-----------------|  
|이름|`xs:string`|이벤트의 사용자 정의 이름입니다.|  
|HostReference|`xs:string`|웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다. 해당 형식은 ' 웹 사이트 이름 응용 프로그램 가상 경로&#124;서비스 가상 경로&#124;ServiceName '으로 정의 됩니다. 예: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.|  
|Payload|`xs:string`|이벤트의 사용자 정의 페이로드입니다.|
