---
description: '자세한 정보: 3508-TrackingProfileNotFound'
title: 3508 - TrackingProfileNotFound
ms.date: 03/30/2017
ms.assetid: 4cee3c4a-0490-4c94-aa19-ef7ce7287c02
ms.openlocfilehash: 3e97af1689a868fb103b06413a0c4f28b0c1f652
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99778011"
---
# <a name="3508---trackingprofilenotfound"></a>3508 - TrackingProfileNotFound

## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|3508|  
|키워드|WFServices|  
|Level|자세히|  
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/분석|  
  
## <a name="description"></a>설명  

 구성 파일에 TrackingProfile이 없거나 ActivityDefinitionId가 프로필과 일치하지 않음을 나타냅니다.  
  
## <a name="message"></a>메시지  

 ActivityDefinitionId '%2'에 대한 TrackingProfile '%1'을(를) 찾지 못했습니다. 구성 파일에 TrackingProfile이 없거나 ActivityDefinitionId가 일치하지 않습니다.  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|TrackingProfile|xs:string|추적 프로필의 이름입니다.|  
|ActivityDefinitionId|xs:string|작업 정의 ID입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
