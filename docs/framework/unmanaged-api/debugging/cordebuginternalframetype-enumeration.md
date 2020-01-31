---
title: CorDebugInternalFrameType 열거형
ms.date: 03/30/2017
api_name:
- CorDebugInternalFrameType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugInternalFrameType
helpviewer_keywords:
- CorDebugInternalFrameType enumeration [.NET Framework debugging]
ms.assetid: e4412dc2-c338-4cfb-94d8-f682095dd2b1
topic_type:
- apiref
ms.openlocfilehash: 2be827e12db765485ee889d6a4a19a982dad5d54
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778363"
---
# <a name="cordebuginternalframetype-enumeration"></a>CorDebugInternalFrameType 열거형
스택 프레임 형식을 식별합니다. 이 열거형은 [ICorDebugInternalFrame:: GetFrameType](icordebuginternalframe-getframetype-method.md) 메서드에서 사용 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum CorDebugInternalFrameType {  
  
    STUBFRAME_NONE                 = 0x00000000,  
    STUBFRAME_M2U                  = 0x00000001,  
    STUBFRAME_U2M                  = 0x00000002,  
    STUBFRAME_APPDOMAIN_TRANSITION = 0x00000003,  
    STUBFRAME_LIGHTWEIGHT_FUNCTION = 0x00000004,  
    STUBFRAME_FUNC_EVAL            = 0x00000005,  
    STUBFRAME_INTERNALCALL         = 0x00000006,  
    STUBFRAME_CLASS_INIT           = 0x00000007,  
    STUBFRAME_EXCEPTION            = 0x00000008,  
    STUBFRAME_SECURITY             = 0x00000009,  
    STUBFRAME_JIT_COMPILATION     = 0x0000000a,  
} CorDebugInternalFrameType;  
```  
  
## <a name="members"></a>Members  
  
|Member|설명|  
|------------|-----------------|  
|`STUBFRAME_NONE`|null 값입니다. `ICorDebugInternalFrame::GetFrameType` 메서드는이 값을 반환 하지 않습니다.|  
|`STUBFRAME_M2U`|관리 되는 관리 되지 않는 스텁 프레임입니다.|  
|`STUBFRAME_U2M`|관리 되지 않는 스텁 프레임입니다.|  
|`STUBFRAME_APPDOMAIN_TRANSITION`|응용 프로그램 도메인 간 전환|  
|`STUBFRAME_LIGHTWEIGHT_FUNCTION`|간단한 메서드 호출입니다.|  
|`STUBFRAME_FUNC_EVAL`|함수 계산의 시작입니다.|  
|`STUBFRAME_INTERNALCALL`|공용 언어 런타임에 대 한 내부 호출입니다.|  
|`STUBFRAME_CLASS_INIT`|클래스 초기화의 시작입니다.|  
|`STUBFRAME_EXCEPTION`|Throw 되는 예외입니다.|  
|`STUBFRAME_SECURITY`|코드 액세스 보안에 사용 되는 프레임입니다.|  
|`STUBFRAME_JIT_COMPILATION`|런타임은 메서드를 JIT 컴파일하는 것입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 열거형](debugging-enumerations.md)
