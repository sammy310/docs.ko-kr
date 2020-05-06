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
ms.openlocfilehash: 7eccaf984b187e463195bb3804f87bbb2c7ad47b
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795926"
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
  
## <a name="members"></a>구성원  
  
|멤버|설명|  
|------------|-----------------|  
|`pModule`|현재 프레임에 대 한 ICorDebugModule 개체에 대 한 포인터입니다.|  
|`ip`|현재 프레임에 대 한 명령 포인터 (EIP/RIP)의 값입니다.|  
|`methodDef`|현재 프레임에 대 한 메서드 토큰입니다.|  
|`isLastForeignExceptionFrame`|프레임이 외부 예외의 마지막 프레임 인지 여부를 나타내는 값입니다.|  
  
## <a name="remarks"></a>설명  
 호출자는 더 이상 사용 되지 않는 경우 ICorDebugModule 개체에 대 한 포인터를 해제 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [디버깅 구조체](debugging-structures.md)
- [디버깅](index.md)
