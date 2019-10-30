---
title: CorDebugExceptionObjectStackFrame 구조체
ms.date: 03/30/2017
api_name:
- CorDebugExceptionObjectStackFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionObjectStackFrame
helpviewer_keywords:
- CorDebugExceptionObjectStackFrame structure [.NET Framework debugging]
ms.assetid: 542cdd81-5ae7-4361-b0ef-1ae4775df258
topic_type:
- apiref
ms.openlocfilehash: faa2082d31c5fa47b87e2238017066b477fdc191
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132171"
---
# <a name="cordebugexceptionobjectstackframe-structure"></a>CorDebugExceptionObjectStackFrame 구조체
예외 개체의 스택 프레임 정보를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct CorDebugExceptionObjectStackFrame {  
    ICorDebugModule* pModule;  
    CORDB_ADDRESS ip;  
    mdMethodDef methodDef;  
    BOOL isLastForeignExceptionFrame;  
} CorDebugExceptionObjectStackFrame;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`pModule`|현재 프레임에 대 한 ICorDebugModule 개체에 대 한 포인터입니다.|  
|`ip`|현재 프레임에 대 한 명령 포인터 (EIP/RIP)의 값입니다.|  
|`methodDef`|현재 프레임에 대 한 메서드 토큰입니다.|  
|`isLastForeignExceptionFrame`|프레임이 외부 예외의 마지막 프레임 인지 여부를 나타내는 값입니다.|  
  
## <a name="remarks"></a>주의  
 호출자는 더 이상 사용 되지 않는 경우 ICorDebugModule 개체에 대 한 포인터를 해제 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 구조체](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
