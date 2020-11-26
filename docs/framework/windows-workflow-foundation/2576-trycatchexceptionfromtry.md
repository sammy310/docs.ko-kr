---
title: 2576 - TryCatchExceptionFromTry
ms.date: 03/30/2017
ms.assetid: 47e48973-b17c-4a16-8338-c84b54aa0a6e
ms.openlocfilehash: 722d5206322c2a9abacbca554d489ba2f6efe357
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96235833"
---
# <a name="2576---trycatchexceptionfromtry"></a>2576 - TryCatchExceptionFromTry

## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|2576|  
|키워드|WFActivities|  
|Level|정보|  
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그|  
  
## <a name="description"></a>Description  

 TryCatch 작업에서 예외를 catch했음을 나타냅니다.  
  
## <a name="message"></a>메시지  

 TryCatch 작업 '%1'에서 '%2' 형식의 예외를 catch했습니다.  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|Description|  
|--------------------|--------------------|-----------------|  
|DisplayName|xs:string|작업의 표시 이름입니다.|  
|예외|xs:string|예외의 형식 이름입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
