---
description: '자세한 정보: 3551-BufferOutOfOrderMessageNoBookmark'
title: 3551 - BufferOutOfOrderMessageNoBookmark
ms.date: 03/30/2017
ms.assetid: 7930d6c4-c843-4a83-933a-cecd71b80d1e
ms.openlocfilehash: 573056fed1753ac55c51d9a074047e8eea15e229
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99777998"
---
# <a name="3551---bufferoutofordermessagenobookmark"></a>3551 - BufferOutOfOrderMessageNoBookmark

## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|3551|  
|키워드|WFServices|  
|Level|정보|  
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/분석|  
  
## <a name="description"></a>설명  

 책갈피 다시 시작이 실패했음을 나타냅니다. 서비스 인스턴스에서 이 특정 작업을 처리할 준비가 되면 다시 버퍼링된 수신 작업이 시도됩니다.  
  
## <a name="message"></a>메시지  

 현재는 서비스 인스턴스 '%1'에서 '%2' 작업을 수행할 수 없습니다. 서비스 인스턴스에서 이 특정 작업을 처리할 준비가 되면 다시 작업이 시도됩니다.  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|OperationName|xs:string|작업의 이름입니다.|  
|ServiceInstanceId|xs:string|서비스 인스턴스의 ID입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
