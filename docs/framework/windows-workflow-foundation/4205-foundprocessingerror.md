---
title: 4205 - FoundProcessingError
ms.date: 03/30/2017
ms.assetid: f2235a15-dd87-439e-8cb9-8b1b89a3dacf
ms.openlocfilehash: 2931d3723a04d7970197c9ebd79dc65ea43d67a7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251245"
---
# <a name="4205---foundprocessingerror"></a>4205 - FoundProcessingError

## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|4205|  
|키워드|WFInstanceStore|  
|Level|오류|  
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그|  
  
## <a name="description"></a>Description  

 SQL 공급자 명령이 실패했음을 나타냅니다.  
  
## <a name="message"></a>메시지  

 명령 실패: %1  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|Description|  
|--------------------|--------------------|-----------------|  
|ExceptionMessage|xs:string|SQL 예외로부터의 메시지입니다.|  
|예외|xs:string|예외에 대한 예외 정보|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
