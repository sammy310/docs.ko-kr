---
title: ICorDebugProcess2::ClearUnmanagedBreakpoint 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.ClearUnmanagedBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::ClearUnmanagedBreakpoint
helpviewer_keywords:
- ClearUnmanagedBreakpoint method [.NET Framework debugging]
- ICorDebugProcess2::ClearUnmanagedBreakpoint method [.NET Framework debugging]
ms.assetid: 12ed0fff-7f0e-4d7a-bb70-b3376371f36c
topic_type:
- apiref
ms.openlocfilehash: 8377ead42c752d8ebe9813d9e00662b94339f8a3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137238"
---
# <a name="icordebugprocess2clearunmanagedbreakpoint-method"></a>ICorDebugProcess2::ClearUnmanagedBreakpoint 메서드
지정 된 주소에서 이전에 설정 된 중단점을 제거 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ClearUnmanagedBreakpoint (  
    [in] CORDB_ADDRESS   address  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `address`  
 진행 중단점이 설정 된 주소를 지정 하는 `CORDB_ADDRESS` 값입니다.  
  
## <a name="remarks"></a>주의  
 지정 된 중단점은 이전에 [ICorDebugProcess2:: SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)에 대 한 호출에 의해 설정 되었습니다.  
  
 디버깅 중인 프로세스가 실행 되는 동안 `ClearUnmanagedBreakpoint` 메서드를 호출할 수 있습니다.  
  
 디버거가 관리 전용 모드로 연결 되어 있거나 지정 된 주소에 중단점이 없는 경우 `ClearUnmanagedBreakpoint` 메서드는 오류 코드를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
