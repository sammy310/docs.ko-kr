---
description: '다음에 대 한 자세한 정보: 39456-TrackingRecordDropped 됨'
title: 39456 - TrackingRecordDropped
ms.date: 03/30/2017
ms.assetid: da13d5bc-1736-47a4-b3fd-064ca8040326
ms.openlocfilehash: 0f6920ef85327318f4ea8662ae36f26c7494bcb2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99631296"
---
# <a name="39456---trackingrecorddropped"></a>39456 - TrackingRecordDropped

## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|39456|  
|키워드|WFTracking|  
|Level|경고|  
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그|  
  
## <a name="description"></a>설명  

 추적 레코드의 크기가 ETW 세션 공급자에서 허용하는 최대값을 초과하기 때문에 추적 레코드가 삭제되었음을 나타냅니다.  
  
## <a name="message"></a>메시지  

 추적 레코드 %1의 크기가 %2 공급자의 ETW 세션에서 허용된 최대값을 초과합니다.  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|예외|xs:string|예외에 대한 예외 정보|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
