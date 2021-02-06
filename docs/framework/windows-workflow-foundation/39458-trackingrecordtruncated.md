---
description: '다음에 대 한 자세한 정보: 39458-TrackingRecordTruncated'
title: 39458 - TrackingRecordTruncated
ms.date: 03/30/2017
ms.assetid: 5352f0eb-d571-454a-bab5-e2162888b218
ms.openlocfilehash: bb9a46dc5bd9bc4f4709a740dd0e7ec47ca826e3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99631283"
---
# <a name="39458---trackingrecordtruncated"></a>39458 - TrackingRecordTruncated

## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|39458|  
|키워드|WFTracking|  
|Level|경고|  
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그|  
  
## <a name="description"></a>설명  

 추적 레코드가 잘렸음을 나타냅니다. 변수/주석/사용자 데이터가 제거되었습니다.  
  
## <a name="message"></a>메시지  

 잘린 추적 레코드 %1이(가) 공급자가 %2인 ETW 세션에 기록되었습니다. 변수/주석/사용자 데이터가 제거되었습니다.  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|RecordNumber|xs:string|추적 레코드 번호입니다.|  
|ProviderId|xs:string|ETW 공급자 ID입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
