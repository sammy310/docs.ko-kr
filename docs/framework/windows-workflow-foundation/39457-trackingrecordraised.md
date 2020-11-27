---
title: 39457 - TrackingRecordRaised
ms.date: 03/30/2017
ms.assetid: 5a2731d1-c731-4b79-bb69-016cb69ef481
ms.openlocfilehash: 5bf343f29528bdb3941e253b2fd5b39799d94c2a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275907"
---
# <a name="39457---trackingrecordraised"></a>39457 - TrackingRecordRaised

## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|39457|  
|키워드|WFRuntime|  
|Level|정보|  
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그|  
  
## <a name="description"></a>Description  

 TrackingRecord가 TrackingParticipant에서 발생했음을 나타냅니다.  
  
## <a name="message"></a>메시지  

 추적 레코드 %1이(가) %2(으)로 증가했습니다.  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|Description|  
|--------------------|--------------------|-----------------|  
|RecordNumber|xs:string|추적 레코드 번호입니다.|  
|ParticipantId|xs:string|추적 참가자입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
