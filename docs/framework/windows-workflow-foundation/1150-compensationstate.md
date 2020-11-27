---
title: 1150 - CompensationState
ms.date: 03/30/2017
ms.assetid: eb015842-cc5a-47be-bce5-6af39e567723
ms.openlocfilehash: 2adb317521b8659c2419e4c04aabf4cf4499b36f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96285111"
---
# <a name="1150---compensationstate"></a>1150 - CompensationState

## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|1150|  
|키워드|WFActivities|  
|Level|정보|  
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그|  
  
## <a name="description"></a>Description  

 CompensableActivity에서 상태 변경을 나타냅니다.  
  
## <a name="message"></a>메시지  

 CompensableActivity '%1'은(는) '%2' 상태입니다.  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|Description|  
|--------------------|--------------------|-----------------|  
|DisplayName|xs:string|작업의 표시 이름입니다.|  
|시스템 상태|xs:string|보정 상태입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
