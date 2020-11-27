---
title: 4206 - UnlockInstanceException
ms.date: 03/30/2017
ms.assetid: 5a46dc5f-d517-4135-8905-25a42f01206b
ms.openlocfilehash: 48182d7c5fe8f29842a17f28c0ea296f93b31089
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251258"
---
# <a name="4206---unlockinstanceexception"></a>4206 - UnlockInstanceException

## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|4206|  
|키워드|WFInstanceStore|  
|Level|오류|  
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그|  
  
## <a name="description"></a>Description  

 인스턴스를 잠금 해제하려는 동안 예외가 발생했음을 나타냅니다.  
  
## <a name="message"></a>메시지  

 인스턴스 잠금을 해제하는 동안 %1 예외가 발생했습니다.  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|Description|  
|--------------------|--------------------|-----------------|  
|ExceptionMessage|xs:string|SQL 예외로부터의 메시지입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
