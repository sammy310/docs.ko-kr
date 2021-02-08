---
description: '자세한 정보: 401-StopSignPostEvent'
title: 401- StopSignPostEvent
ms.date: 03/30/2017
ms.assetid: e033d03a-510d-4300-aa65-ef02cb4807f2
ms.openlocfilehash: 99b6151d902f3f8059b0aa01e6cda290debafda6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793950"
---
# <a name="401--stopsignpostevent"></a>401- StopSignPostEvent

## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|401|  
|키워드|문제 해결|  
|Level|정보|  
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/분석|  
  
## <a name="description"></a>설명  

 이 이벤트는 엔드투엔드 동작의 끝을 표시합니다. 여기에는 동작의 이름이 포함됩니다.  
  
## <a name="message"></a>메시지  

 동작 경계입니다.  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|Extended Data|`xs:string`|작업의 이름입니다.|  
|AppDomain|`xs:string`|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
