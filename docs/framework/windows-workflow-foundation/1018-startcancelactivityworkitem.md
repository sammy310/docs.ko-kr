---
description: '자세한 정보: 1018-StartCancelActivityWorkItem'
title: 1018 - StartCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 68b4fa1d-eee6-4a2a-8c16-7e9d89f08ab9
ms.openlocfilehash: 99da17bd2fb75d9ed3a41e95ec1929df66964ffd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792884"
---
# <a name="1018---startcancelactivityworkitem"></a>1018 - StartCancelActivityWorkItem

## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|1018|  
|키워드|WFRuntime|  
|Level|자세히|  
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그|  
  
## <a name="description"></a>설명  

 CancelActivityWorkItem이 실행을 시작했음을 나타냅니다.  
  
## <a name="message"></a>메시지  

 작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 CancelActivityWorkItem의 실행을 시작합니다.  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|활동|xs:string|작업의 형식 이름입니다.|  
|DisplayName|xs:string|작업의 표시 이름입니다.|  
|InstanceId|xs:string|작업의 인스턴스 ID입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
