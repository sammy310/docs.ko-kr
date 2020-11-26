---
title: 3507 - ServiceEndpointAdded
ms.date: 03/30/2017
ms.assetid: c068fc0e-07ee-4551-9824-ea7216e1fe37
ms.openlocfilehash: 903071e7b1f89dc3489b8d3ac05427d699a33a7e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96240760"
---
# <a name="3507---serviceendpointadded"></a>3507 - ServiceEndpointAdded

## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|3507|  
|키워드|WFServices|  
|Level|정보|  
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/분석|  
  
## <a name="description"></a>Description  

 서비스 엔드포인트가 추가되었음을 나타냅니다.  
  
## <a name="message"></a>메시지  

 주소 '%1', 바인딩 '%2' 및 계약 '%3'에 대해 서비스 엔드포인트가 추가되었습니다.  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|Description|  
|--------------------|--------------------|-----------------|  
|주소|xs:string|엔드포인트의 주소입니다.|  
|바인딩|xs:string|엔드포인트의 바인딩입니다.|  
|계약|xs:string|엔드포인트의 계약입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
