---
description: '자세한 정보: 1146-FlowchartSwitchCase'
title: 1146 - FlowchartSwitchCase
ms.date: 03/30/2017
ms.assetid: 274e9209-1720-4512-a615-e742f00895f4
ms.openlocfilehash: f6e9b33f9c068b51695d3ac46cda51fb6d9f8b3f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667072"
---
# <a name="1146---flowchartswitchcase"></a>1146 - FlowchartSwitchCase

## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|1146|  
|키워드|WFActivities|  
|Level|정보|  
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그|  
  
## <a name="description"></a>설명  

 Flowchart 스위치에서 Case가 선택되었음을 나타냅니다.  
  
## <a name="message"></a>메시지  

 Flowchart '%1'/FlowSwitch - Case '%2'을(를) 선택했습니다.  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|FlowChart|xs:string|FlowChart의 표시 이름입니다.|  
|사례|xs:string|switch case가 선택되었습니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
