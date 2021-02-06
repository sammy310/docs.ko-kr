---
description: '자세한 정보: 39460-TrackingValueNotSerializable'
title: 39460 - TrackingValueNotSerializable
ms.date: 03/30/2017
ms.assetid: 476a29ad-24d8-4359-8c17-d4e20c1e1c15
ms.openlocfilehash: d53406344b4683876615c3859721891ef7588ee9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99631270"
---
# <a name="39460---trackingvaluenotserializable"></a>39460 - TrackingValueNotSerializable

## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|39460|  
|키워드|WFTracking|  
|Level|경고|  
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그|  
  
## <a name="description"></a>설명  

 추적 레코드에서 추출된 인수/변수는 Serialize할 수 없습니다.  
  
## <a name="message"></a>메시지  

 추출된 인수/변수 '%1'은(는) serialize할 수 없습니다.  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|Name|xs:string|항목의 이름입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
