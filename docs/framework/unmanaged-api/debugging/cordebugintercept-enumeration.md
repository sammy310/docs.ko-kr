---
title: CorDebugIntercept 열거형
ms.date: 03/30/2017
api_name:
- CorDebugIntercept
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugIntercept
helpviewer_keywords:
- CorDebugIntercept enumeration [.NET Framework debugging]
ms.assetid: 3d5b642e-7ef2-428b-a5ae-509c35ed461a
topic_type:
- apiref
ms.openlocfilehash: 8ce48b63a92e84ce92da0dcf35a6242744c1a8c3
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778426"
---
# <a name="cordebugintercept-enumeration"></a>CorDebugIntercept 열거형
가로챌 수 있는(즉, 한 단계씩 실행할 수 있는) 코드 형식을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum CorDebugIntercept {  
    INTERCEPT_NONE                = 0x0,  
    INTERCEPT_CLASS_INIT          = 0x01,  
    INTERCEPT_EXCEPTION_FILTER    = 0x02,  
    INTERCEPT_SECURITY            = 0x04,  
    INTERCEPT_CONTEXT_POLICY      = 0x08,  
    INTERCEPT_INTERCEPTION        = 0x10,  
    INTERCEPT_ALL                 = 0xffff  
} CorDebugIntercept;  
```  
  
## <a name="members"></a>Members  
  
|Member|설명|  
|------------|-----------------|  
|`INTERCEPT_NONE`|코드를 가로챌 수 없습니다.|  
|`INTERCEPT_CLASS_INIT`|생성자를 가로챌 수 있습니다.|  
|`INTERCEPT_EXCEPTION_FILTER`|예외 필터를 가로챌 수 있습니다.|  
|`INTERCEPT_SECURITY`|보안을 적용 하는 코드를 가로챌 수 있습니다.|  
|`INTERCEPT_CONTEXT_POLICY`|컨텍스트 정책을 가로챌 수 있습니다.|  
|`INTERCEPT_INTERCEPTION`|사용되지 않습니다.|  
|`INTERCEPT_ALL`|모든 코드를 가로챌 수 있습니다.|  
  
## <a name="remarks"></a>주의  
 Use the [ICorDebugStepper::SetInterceptMask](icordebugstepper-setinterceptmask-method.md) method to establish the types of code that can be intercepted.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 열거형](debugging-enumerations.md)
