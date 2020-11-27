---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: f1978881517fe5010ccc0f5192b21bd6688f063a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96291117"
---
# <a name="activitytransfer"></a>ActivityTransfer

활동 전송 이벤트  
  
## <a name="syntax"></a>구문  
  
```csharp
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a>메서드  

 ActivityTransfer 클래스는 메서드를 정의하지 않습니다.  
  
## <a name="properties"></a>속성  

 ActivityTransfer 클래스에는 다음 속성이 포함되어 있습니다.  
  
### <a name="activityid"></a>ActivityID  
  
- 데이터 형식: object  
    액세스 형식: 읽기 전용  
  
- 활동 ID  
  
### <a name="relatedactivityid"></a>RelatedActivityID  
  
- 데이터 형식: object  
    액세스 형식: 읽기 전용  
  
- 관련 활동 ID  
  
## <a name="requirements"></a>요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|-----------------------------------|  
|네임스페이스|root\ServiceModel에 정의되어 있습니다.|
