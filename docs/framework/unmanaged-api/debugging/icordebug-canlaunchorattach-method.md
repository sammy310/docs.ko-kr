---
title: ICorDebug::CanLaunchOrAttach 메서드
ms.date: 03/30/2017
api_name:
- ICorDebug.CanLaunchOrAttach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::CanLaunchOrAttach
helpviewer_keywords:
- ICorDebug::CanLaunchOrAttach method [.NET Framework debugging]
- CanLaunchOrAttach method [.NET Framework debugging]
ms.assetid: ca7723db-7c07-4cdd-bd92-fba34928b623
topic_type:
- apiref
ms.openlocfilehash: 354df02b27e87550ba602fe102352455c227441b
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859679"
---
# <a name="icordebugcanlaunchorattach-method"></a>ICorDebug::CanLaunchOrAttach 메서드
현재 컴퓨터 및 런타임 구성의 컨텍스트 내에서 새 프로세스를 시작 하거나 지정 된 기존 프로세스에 연결할 수 있는지 여부를 나타내는 HRESULT를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CanLaunchOrAttach (  
    [in] DWORD      dwProcessId,  
    [in] BOOL       win32DebuggingEnabled  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `dwProcessId`  
 진행 기존 프로세스의 ID입니다.  
  
 `win32DebuggingEnabled`  
 진행 Win32 디버깅 `true` 을 사용 하도록 설정 하 여를 시작 하려는 경우 또는 win32 디버깅을 사용 하도록 설정 된 연결을 사용 하 여를 전달 합니다. 그렇지 않으면를 `false`전달 합니다.  
  
## <a name="return-value"></a>Return Value  
 현재 컴퓨터와 런타임 구성에 대 한 정보를 고려 하 여 디버깅 서비스에서 새 프로세스를 시작 하거나 지정 된 프로세스에 연결 하는 것이 가능한 지 확인 하는 경우에 S_OK 합니다. 가능한 HRESULT 값은 다음과 같습니다.  
  
- S_OK  
  
- CORDBG_E_DEBUGGING_NOT_POSSIBLE  
  
- CORDBG_E_KERNEL_DEBUGGER_PRESENT  
  
- CORDBG_E_KERNEL_DEBUGGER_ENABLED  
  
## <a name="remarks"></a>설명  
 이 메서드는 전적으로 정보를 제공 합니다. 인터페이스는에서 `CanLaunchOrAttach`반환 된 값에 관계 없이 프로세스를 시작 하거나 프로세스에 연결 하는 것을 중지 하지 않습니다.  
  
 Win32 디버깅을 사용 하도록 설정 하거나 Win32 디버깅을 사용 하도록 설정한 상태에서를 시작 `true` 하려는 `win32DebuggingEnabled`경우에는를 전달 합니다. 이 옵션을 사용 `CanLaunchOrAttach` 하는 경우에 의해 반환 되는 HRESULT는 다를 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorDebug 인터페이스](icordebug-interface.md)
