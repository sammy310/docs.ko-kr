---
title: ICorDebugFrame::GetStackRange 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetStackRange
helpviewer_keywords:
- GetStackRange method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetStackRange method [.NET Framework debugging]
ms.assetid: fab037cb-fda6-40fb-9367-921e435dd5a0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 43532888d181adcb7a7e3760f2a5e3d8f664a35c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492285"
---
# <a name="icordebugframegetstackrange-method"></a>ICorDebugFrame::GetStackRange 메서드
이 스택 프레임의 절대 주소 범위를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pStart`  
 [out] 에 대 한 포인터를 `CORDB_ADDRESS` 이 나타내는 스택 프레임의 시작 주소를 지정 하는 `ICorDebugFrame` 개체입니다.  
  
 `pEnd`  
 [out] 에 대 한 포인터를 `CORDB_ADDRESS` 이 나타내는 스택 프레임의 끝 주소를 지정 하는 `ICorDebugFrame` 개체입니다.  
  
## <a name="remarks"></a>설명  
 스택의 주소 범위는 여러 디버깅 엔진에서 수집 된 인터리브된 스택 추적 하나로 결합 유용 합니다. 숫자 범위 스택 프레임의 내용 관련 정보를 제공합니다. 것은 스택 프레임 위치 비교에 대해서만 의미가 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
