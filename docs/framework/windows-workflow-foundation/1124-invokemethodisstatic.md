---
description: '자세한 정보: 1124-InvokeMethodIsStatic'
title: 1124 - InvokeMethodIsStatic
ms.date: 03/30/2017
ms.assetid: b9643641-fb52-4fa8-b354-4dd6617d68f6
ms.openlocfilehash: 86febd9c94c2e4c533eb5ab4349855f6d048a5ae
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667384"
---
# <a name="1124---invokemethodisstatic"></a>1124 - InvokeMethodIsStatic

## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|1124|  
|키워드|WFRuntime|  
|Level|정보|  
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그|  
  
## <a name="description"></a>설명  

 CacheMetadata 단계 중 InvokeMethod 작업에서 호출할 메서드가 정적임을 나타냅니다.  
  
## <a name="message"></a>메시지  

 InvokeMethod '%1' - 메서드가 Static입니다.  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|InvokeMethod|xs:string|InvokeMethod 작업의 표시 이름입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
