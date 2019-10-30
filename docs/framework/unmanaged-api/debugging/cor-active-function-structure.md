---
title: COR_ACTIVE_FUNCTION 구조체
ms.date: 03/30/2017
api_name:
- COR_ACTIVE_FUNCTION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_ACTIVE_FUNCTION
helpviewer_keywords:
- COR_ACTIVE_FUNCTION structure [.NET Framework debugging]
ms.assetid: ed86185f-2152-459c-961f-10c06d62e83f
topic_type:
- apiref
ms.openlocfilehash: cbc272070e9eb6810b34ec1f3fdc9e944c624cd3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132377"
---
# <a name="cor_active_function-structure"></a>COR_ACTIVE_FUNCTION 구조체
스레드 프레임에서 현재 활성 상태인 함수에 대한 정보를 포함합니다. 이 구조는 [ICorDebugThread2:: GetActiveFunctions](icordebugthread2-getactivefunctions-method.md) 메서드에서 사용 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct  _COR_ACTIVE_FUNCTION {  
    ICorDebugAppDomain   *pAppDomain;  
    ICorDebugModule      *pModule;  
    ICorDebugFunction2   *pFunction;  
    ULONG32              ilOffset;  
    ULONG32              flags;  
} COR_ACTIVE_FUNCTION;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`pAppDomain`|`ilOffset` 필드의 응용 프로그램 도메인 소유자에 대 한 포인터입니다.|  
|`pModule`|`ilOffset` 필드의 모듈 소유자에 대 한 포인터입니다.|  
|`pFunction`|`ilOffset` 필드의 함수 소유자에 대 한 포인터입니다.|  
|`ilOffset`|프레임의 MSIL (Microsoft 중간 언어) 오프셋입니다.|  
|`flags`|향후 확장성을 위해 예약 되었습니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug .idl  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 구조체](debugging-structures.md)
- [디버깅](index.md)
