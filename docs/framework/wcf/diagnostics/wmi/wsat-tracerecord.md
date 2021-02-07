---
description: '다음에 대 한 자세한 정보: WSAT_TraceRecord'
title: WSAT_TraceRecord
ms.date: 03/30/2017
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
ms.openlocfilehash: 67202c5d2910783c40b934d2da6108e6b514a728
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99756879"
---
# <a name="wsat_tracerecord"></a>WSAT_TraceRecord

WSAT_TraceRecord  
  
## <a name="syntax"></a>Syntax  
  
```csharp
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a>메서드  

 WSAT_TraceRecord 클래스는 메서드를 정의하지 않습니다.  
  
## <a name="properties"></a>속성  

 WSAT_TraceRecord 클래스에는 다음과 같은 속성이 있습니다.  
  
### <a name="activityid"></a>ActivityID  

 데이터 형식: object  
액세스 형식: 읽기 전용  
  
 추적 레코드의 동작 ID입니다.  
  
### <a name="eventid"></a>EventID  

 데이터 형식: sint32  
액세스 형식: 읽기 전용  
  
 추적 레코드의 이벤트 ID입니다.  
  
### <a name="tracerecord"></a>TraceRecord  

 데이터 형식: 문자열  
액세스 형식: 읽기 전용  
  
 추적 레코드  
  
## <a name="requirements"></a>요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|-----------------------------------|  
|네임스페이스|root\ServiceModel에 정의되어 있습니다.|
