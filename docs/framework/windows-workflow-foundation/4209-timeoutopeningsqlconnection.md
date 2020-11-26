---
title: 4209 - TimeoutOpeningSqlConnection
ms.date: 03/30/2017
ms.assetid: f0e56518-9758-41dc-a760-50d1a10fba6e
ms.openlocfilehash: 9aa8cdffebb0cdf8b1e8225a394edf78ecf032b9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238680"
---
# <a name="4209---timeoutopeningsqlconnection"></a>4209 - TimeoutOpeningSqlConnection

## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|4209|  
|키워드|WFInstanceStore|  
|Level|오류|  
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그|  
  
## <a name="description"></a>Description  

 SQL 연결을 여는 동안 시간 초과가 발생했음을 나타냅니다.  
  
## <a name="message"></a>메시지  

 SQL 연결을 열려는 중 시간이 초과했습니다. 할당된 시간 제한인 %1 내에 작업을 완료하지 못했습니다. 이 작업에 할당된 시간은 더 긴 시간 제한의 일부였을 수 있습니다.  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|Description|  
|--------------------|--------------------|-----------------|  
|제한 시간|xs:string|SQL 연결을 열기 위한 시간 제한 값입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
