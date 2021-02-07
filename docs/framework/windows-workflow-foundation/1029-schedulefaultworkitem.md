---
description: '자세한 정보: 1029-ScheduleFaultWorkItem'
title: 1029 - ScheduleFaultWorkItem
ms.date: 03/30/2017
ms.assetid: 3a56b29e-f740-459d-8576-d81e58bf5a03
ms.openlocfilehash: e5f0463626882d6c8c48412326582fafa7be4670
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755449"
---
# <a name="1029---schedulefaultworkitem"></a>1029 - ScheduleFaultWorkItem

## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|1029|  
|키워드|WFRuntime|  
|Level|자세히|  
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그|  
  
## <a name="description"></a>설명  

 FaultWorkItem이 예약되었음을 나타냅니다.  
  
## <a name="message"></a>메시지  

 작업 ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 '에 대해 FaultWorkItem이 예약 되었습니다.  작업 '%4', DisplayName: '%5', InstanceId: '%6'에서 예외가 전파되었습니다.  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|FaultActivity|xs:string|오류 작업의 형식 이름입니다.|  
|FaultActivityDisplayName|xs:string|오류 작업의 표시 이름입니다.|  
|FaultActivityInstanceId|xs:string|오류 작업의 인스턴스 ID입니다.|  
|ExceptionActivity|xs:string|예외를 throw한 작업의 형식 이름입니다.|  
|ExceptionActivityDisplayName|xs:string|예외를 throw한 작업의 표시 이름입니다.|  
|ExceptionActivityInstanceId|xs:string|예외를 throw한 작업의 인스턴스 ID입니다.|  
|예외|xs:string|예외에 대한 예외 정보|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
