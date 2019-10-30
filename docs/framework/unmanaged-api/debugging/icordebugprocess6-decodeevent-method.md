---
title: ICorDebugProcess6::DecodeEvent 메서드
ms.date: 03/30/2017
ms.assetid: 1453bc0c-6e0d-4d5a-b176-22607f8a3e6c
ms.openlocfilehash: fd0fba04fe3df0ada8b0b56280906beefb26bb26
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123509"
---
# <a name="icordebugprocess6decodeevent-method"></a>ICorDebugProcess6::DecodeEvent 메서드
특수하게 작성된 네이티브 예외 디버그 이벤트의 페이로드에서 캡슐화된 관리되는 디버그 이벤트를 디코딩합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DecodeEvent(  
        [in, length_is(countBytes), size_is(countBytes)]  const BYTE pRecord[],  
        [in] DWORD countBytes,  
        [in] CorDebugRecordFormat format,  
        [in] DWORD dwFlags,   
        [in] DWORD dwThreadId,   
        [out] ICorDebugDebugEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pRecord`  
 [in] 관리되는 디버그 이벤트에 대한 정보를 포함하는 네이티브 예외 디버그 이벤트의 바이트 배열에 대한 포인터입니다.  
  
 `countBytes`  
 [in] `pRecord` 바이트 배열의 요소 수입니다.  
  
 `format`  
 진행 관리 되지 않는 디버그 이벤트의 형식을 지정 하는 [CorDebugRecordFormat](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md) 열거형 멤버입니다.  
  
 `dwFlags`  
 [in] 대상 아키텍처를 사용하며 디버그 이벤트에 대한 추가 정보를 지정하는 비트 필드입니다. Windows 시스템의 경우 [CorDebugDecodeEventFlagsWindows](../../../../docs/framework/unmanaged-api/debugging/cordebugdecodeeventflagswindows-enumeration.md) 열거의 멤버일 수 있습니다.  
  
 `dwThreadId`  
 [in] 예외가 throw된 스레드의 운영 체제 식별자입니다.  
  
 `ppEvent`  
 제한이 디코딩된 관리 되는 디버그 이벤트를 나타내는 [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>주의  
  
> [!NOTE]
> 이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugProcess6 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
