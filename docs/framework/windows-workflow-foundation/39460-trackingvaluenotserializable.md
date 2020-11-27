---
title: 39460 - TrackingValueNotSerializable
ms.date: 03/30/2017
ms.assetid: 476a29ad-24d8-4359-8c17-d4e20c1e1c15
ms.openlocfilehash: 0ffa33f78f0f3c4eaf2c7519ac27207c095d8c17
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275855"
---
# <a name="39460---trackingvaluenotserializable"></a>39460 - TrackingValueNotSerializable

## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|39460|  
|키워드|WFTracking|  
|Level|경고|  
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그|  
  
## <a name="description"></a>Description  

 추적 레코드에서 추출된 인수/변수는 Serialize할 수 없습니다.  
  
## <a name="message"></a>메시지  

 추출된 인수/변수 '%1'은(는) serialize할 수 없습니다.  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|Description|  
|--------------------|--------------------|-----------------|  
|이름|xs:string|항목의 이름입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
