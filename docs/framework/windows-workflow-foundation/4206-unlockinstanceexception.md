---
description: '자세한 정보: 4206-UnlockInstanceException'
title: 4206 - UnlockInstanceException
ms.date: 03/30/2017
ms.assetid: 5a46dc5f-d517-4135-8905-25a42f01206b
ms.openlocfilehash: 7c281b7471869fc2361b1c7fb158559e4c9fae65
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99676276"
---
# <a name="4206---unlockinstanceexception"></a>4206 - UnlockInstanceException

## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|4206|  
|키워드|WFInstanceStore|  
|Level|Error|  
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그|  
  
## <a name="description"></a>설명  

 인스턴스를 잠금 해제하려는 동안 예외가 발생했음을 나타냅니다.  
  
## <a name="message"></a>메시지  

 인스턴스 잠금을 해제하는 동안 %1 예외가 발생했습니다.  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|ExceptionMessage|xs:string|SQL 예외로부터의 메시지입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
