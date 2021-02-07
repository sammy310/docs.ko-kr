---
description: '자세한 정보: 451-MessageLogInfo'
title: 451 - MessageLogInfo
ms.date: 03/30/2017
ms.assetid: 485b4b29-dc21-4a35-93f8-5f4726d6aa5a
ms.openlocfilehash: 9df1911eaee3300b770175f2af26e6dafd3de90c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760279"
---
# <a name="451---messageloginfo"></a>451 - MessageLogInfo

## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|451|  
|키워드|문제 해결, WCFMessageLogging|  
|Level|정보|  
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/분석|  
  
## <a name="description"></a>설명  

 이 이벤트는 메시지 로그 정보가 전송될 때 내보내집니다.  
  
## <a name="message"></a>메시지  

 %1  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|data1|`xs:string`||  
|AppDomain|`xs:string`|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
