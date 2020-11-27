---
title: 440 - StartSignpostEvent
ms.date: 03/30/2017
ms.assetid: 27b551b5-ae76-49f8-bab8-6300009eb4c1
ms.openlocfilehash: 1e0278d665a961afab21445ab8490e3e5a94987c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293457"
---
# <a name="440---startsignpostevent1"></a>440 - StartSignpostEvent

## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|440|  
|키워드|문제 해결|  
|Level|정보|  
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/분석|  
  
## <a name="description"></a>Description  

 동작 추적에서 보내거나 받을 메시지가 동작 경계를 넘기 시작했음을 나타냅니다.  
  
## <a name="message"></a>메시지  

 동작 경계입니다.  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|Description|  
|--------------------|--------------------|-----------------|  
|ExtendedData|`xs:string`|작업의 이름입니다.|  
|AppDomain|`xs:string`|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
