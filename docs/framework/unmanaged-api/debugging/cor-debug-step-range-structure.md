---
description: '다음에 대 한 자세한 정보: COR_DEBUG_STEP_RANGE 구조체'
title: COR_DEBUG_STEP_RANGE 구조체
ms.date: 03/30/2017
api_name:
- COR_DEBUG_STEP_RANGE
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_DEBUG_STEP_RANGE
helpviewer_keywords:
- COR_DEBUG_STEP_RANGE structure [.NET Framework debugging]
ms.assetid: 8809d00e-beaa-4dcf-b4e8-e89d0a5406b7
topic_type:
- apiref
ms.openlocfilehash: 40462be4b165351b3265fa0833d19f18e0fa3a37
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801841"
---
# <a name="cor_debug_step_range-structure"></a>COR_DEBUG_STEP_RANGE 구조체

코드 범위에 대한 오프셋 정보를 포함합니다.  
  
 이 구조는 [ICorDebugStepper:: StepRange](icordebugstepper-steprange-method.md) 메서드에서 사용 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct {  
    ULONG32 startOffset;  
    ULONG32 endOffset;  
} COR_DEBUG_STEP_RANGE;  
```  
  
## <a name="members"></a>구성원  
  
|멤버|설명|  
|------------|-----------------|  
|`startOffset`|범위의 시작 오프셋입니다.|  
|`endOffset`|범위 끝의 오프셋입니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug .idl  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [StepRange 메서드](icordebugstepper-steprange-method.md)
- [디버깅 구조체](debugging-structures.md)
- [디버깅](index.md)
