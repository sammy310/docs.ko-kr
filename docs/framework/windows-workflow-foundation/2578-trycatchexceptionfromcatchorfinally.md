---
description: '자세한 정보: 2578-TryCatchExceptionFromCatchOrFinally'
title: 2578 - TryCatchExceptionFromCatchOrFinally
ms.date: 03/30/2017
ms.assetid: 4803fee6-b8d8-4937-9907-d5c5fd5299db
ms.openlocfilehash: 7a159d096307d3354695d831db168990be18a236
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99631504"
---
# <a name="2578---trycatchexceptionfromcatchorfinally"></a>2578 - TryCatchExceptionFromCatchOrFinally

## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|2578|  
|키워드|WFActivities|  
|Level|경고|  
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그|  
  
## <a name="description"></a>설명  

 Catch 또는 Finally 작업에서 예외가 throw되었음을 나타냅니다.  
  
## <a name="message"></a>메시지  

 TryCatch 작업 '%1'에 연결된 Catch 또는 Finally 작업에서 예외가 throw되었습니다.  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|Description|  
|--------------------|--------------------|-----------------|  
|DisplayName|xs:string|작업의 표시 이름입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
