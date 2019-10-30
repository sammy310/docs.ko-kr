---
title: ICorDebugFunction2::SetJMCStatus 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::SetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 22c27b01-2869-4214-b840-5921f7c874fc
topic_type:
- apiref
ms.openlocfilehash: 758364b2d63343e464b727d5a1c1817533a6acea
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137790"
---
# <a name="icordebugfunction2setjmcstatus-method"></a>ICorDebugFunction2::SetJMCStatus 메서드
내 코드만 단계별 실행을 위해이 ICorDebugFunction2가 나타내는 함수를 표시 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `bIsJustMyCode`  
 진행 함수를 사용자 코드로 표시 하려면 `true`로 설정 합니다. 그렇지 않으면 `false`로 설정 합니다.  
  
## <a name="return-values"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|`S_OK`|함수가로 표시 되었습니다.|  
|`CORDBG_E_FUNCTION_NOT_DEBUGGABLE`|디버깅할 수 없으므로 함수를 사용자 코드로 표시할 수 없습니다.|  
  
## <a name="remarks"></a>주의  
 내 코드만 스텝 퍼는 사용자가 아닌 코드를 건너뜁니다. 사용자 코드는 디버깅 가능한 코드의 하위 집합 이어야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
