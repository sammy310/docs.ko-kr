---
description: '자세한 정보: 1013-CompleteExecuteActivityWorkItem'
title: 1013 - CompleteExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 31fc57b3-ef2f-48f0-a5de-b4e2c5c9ded7
ms.openlocfilehash: 815f859c40a02e8c06e44603a80ab964dc4e64bd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792949"
---
# <a name="1013---completeexecuteactivityworkitem"></a>1013 - CompleteExecuteActivityWorkItem

## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|1013|  
|키워드|WFRuntime|  
|Level|자세히|  
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그|  
  
## <a name="description"></a>설명  

 ExecuteActivityWorkItem이 완료되었음을 나타냅니다.  
  
## <a name="message"></a>메시지  

 작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 ExecuteActivityWorkItem이 완료되었습니다.  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|활동|xs:string|작업의 형식 이름입니다.|  
|DisplayName|xs:string|작업의 표시 이름입니다.|  
|InstanceId|xs:string|작업의 인스턴스 ID입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
