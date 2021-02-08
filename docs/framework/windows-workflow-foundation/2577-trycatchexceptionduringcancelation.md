---
description: '자세한 정보: 2577-TryCatchExceptionDuringCancelation'
title: 2577 - TryCatchExceptionDuringCancelation
ms.date: 03/30/2017
ms.assetid: 35ee9f55-227f-4566-bcb4-4c7c75dea85b
ms.openlocfilehash: e02e7722dadfe38b9fc1fbb92e809ae8f80cbd2f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99778102"
---
# <a name="2577---trycatchexceptionduringcancelation"></a>2577 - TryCatchExceptionDuringCancelation

## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|2577|  
|키워드|WFActivities|  
|Level|경고|  
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그|  
  
## <a name="description"></a>설명  

 취소하는 동안 TryCatch 작업의 자식 작업에서 예외가 throw되었음을 나타냅니다.  
  
## <a name="message"></a>메시지  

 취소하는 동안 TryCatch 작업 '%1'의 자식 작업에서 예외가 throw되었습니다.  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|Description|  
|--------------------|--------------------|-----------------|  
|DisplayName|xs:string|작업의 표시 이름입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
