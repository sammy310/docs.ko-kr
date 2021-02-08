---
description: '자세한 정보: 3503-DuplicateCorrelationQuery'
title: 3503 - DuplicateCorrelationQuery
ms.date: 03/30/2017
ms.assetid: b857f8e6-ce4d-4da4-bc9d-6cd63fa558a4
ms.openlocfilehash: a8e1e41aad3aa1b273d8f8a5d7b0768fabe4e658
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99778076"
---
# <a name="3503---duplicatecorrelationquery"></a>3503 - DuplicateCorrelationQuery

## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|3503|  
|키워드|WFServices|  
|Level|경고|  
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/분석|  
  
## <a name="description"></a>설명  

 중복 CorrelationQuery를 찾았음을 나타냅니다. 중복 쿼리는 상관 관계를 계산할 때 사용되지 않습니다.  
  
## <a name="message"></a>메시지  

 Where='%1'인 중복 CorrelationQuery가 있습니다. 이 중복 쿼리는 상관 관계를 계산할 때 사용되지 않습니다.  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|Where|xs:string|상관 관계 쿼리의 Where 부분입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
