---
title: ICorDebug::DebugActiveProcess 메서드
ms.date: 03/30/2017
api_name:
- ICorDebug.DebugActiveProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::DebugActiveProcess
helpviewer_keywords:
- DebugActiveProcess method [.NET Framework debugging]
- ICorDebug::DebugActiveProcess method [.NET Framework debugging]
ms.assetid: fdab0ade-7f56-4fa2-b3ef-f7a1d2852bba
topic_type:
- apiref
ms.openlocfilehash: 3630e25b6c24edaa366f1b0fae088e760e851fa4
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895404"
---
# <a name="icordebugdebugactiveprocess-method"></a>ICorDebug::DebugActiveProcess 메서드
디버거를 기존 프로세스에 연결 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DebugActiveProcess (  
    [in]  DWORD               id,  
    [in]  BOOL                win32Attach,  
    [out] ICorDebugProcess    **ppProcess  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `id`  
 진행 디버거를 연결할 프로세스의 ID입니다.  
  
 `win32Attach`  
 진행 디버거가 프로세스에 대 한 Win32 `true` 디버거로 동작 하 고 관리 되지 않는 콜백을 디스패치할 경우로 설정 되는 부울 값입니다. 그렇지 않으면 `false`입니다.  
  
 `ppProcess`  
 제한이 디버거가 연결 된 프로세스를 나타내는 "ICorDebugProcess" 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 IA-64 기반 및 AMD64 기반 플랫폼과 같은 Win9x 및 비 x86 플랫폼에서는 Interop 디버깅이 지원 되지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebug 인터페이스](icordebug-interface.md)
