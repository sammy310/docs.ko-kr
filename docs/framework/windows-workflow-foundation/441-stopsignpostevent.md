---
title: 441- StopSignPostEvent
ms.date: 03/30/2017
ms.assetid: fc9850a5-0dc3-4b84-a09a-744301c7c18e
ms.openlocfilehash: fc78fcd6c8048ed4ae861ceaf92eac3500e018b5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267158"
---
# <a name="441--stopsignpostevent1"></a>441- StopSignPostEvent

## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|441|  
|키워드|문제 해결|  
|Level|정보|  
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/분석|  
  
## <a name="description"></a>Description  

 동작 추적에서 보내거나 받을 메시지가 동작 경계 넘기를 완료했음을 나타냅니다.  
  
## <a name="message"></a>메시지  

 동작 경계입니다.  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|Description|  
|--------------------|--------------------|-----------------|  
|Extended Data|`xs:string`|작업의 이름입니다.|  
|AppDomain|`xs:string`|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
