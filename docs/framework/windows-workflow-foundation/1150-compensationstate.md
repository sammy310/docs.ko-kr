---
description: '자세한 정보: 1150-CompensationState'
title: 1150 - CompensationState
ms.date: 03/30/2017
ms.assetid: eb015842-cc5a-47be-bce5-6af39e567723
ms.openlocfilehash: 4adc246cbe46dee3594bc6c0330c8e0306489219
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99703343"
---
# <a name="1150---compensationstate"></a>1150 - CompensationState

## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|1150|  
|키워드|WFActivities|  
|Level|정보|  
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그|  
  
## <a name="description"></a>설명  

 CompensableActivity에서 상태 변경을 나타냅니다.  
  
## <a name="message"></a>메시지  

 CompensableActivity '%1'은(는) '%2' 상태입니다.  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|Description|  
|--------------------|--------------------|-----------------|  
|DisplayName|xs:string|작업의 표시 이름입니다.|  
|시스템 상태|xs:string|보정 상태입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
