---
title: 39458 - TrackingRecordTruncated
ms.date: 03/30/2017
ms.assetid: 5352f0eb-d571-454a-bab5-e2162888b218
ms.openlocfilehash: f02a34673c51be6e0b127a64e4622131575d836f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275894"
---
# <a name="39458---trackingrecordtruncated"></a>39458 - TrackingRecordTruncated

## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|39458|  
|키워드|WFTracking|  
|Level|경고|  
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그|  
  
## <a name="description"></a>Description  

 추적 레코드가 잘렸음을 나타냅니다. 변수/주석/사용자 데이터가 제거되었습니다.  
  
## <a name="message"></a>메시지  

 잘린 추적 레코드 %1이(가) 공급자가 %2인 ETW 세션에 기록되었습니다. 변수/주석/사용자 데이터가 제거되었습니다.  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|Description|  
|--------------------|--------------------|-----------------|  
|RecordNumber|xs:string|추적 레코드 번호입니다.|  
|ProviderId|xs:string|ETW 공급자 ID입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
