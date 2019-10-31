---
title: CorDebugStateChange 열거형
ms.date: 02/07/2019
api_name:
- CorDebugStateChange
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 1d4424ab-5143-4e50-a84a-ceeb4ddf3bba
topic_type:
- apiref
ms.openlocfilehash: 239e3a82df0e6010278669f9f429bfad0d163319
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133720"
---
# <a name="cordebugstatechange-enumeration"></a>CorDebugStateChange 열거형

프로세스에 대한 변경 내용을 기반으로 삭제해야 하는 캐시된 데이터의 양을 설명합니다.

## <a name="syntax"></a>구문

```cpp
typedef enum CorDebugStateChange
{
    PROCESS_RUNNING = 0x0000001,
    FLUSH_ALL       = 0x0000002,
} CorDebugStateChange;
```

## <a name="members"></a>멤버

| 멤버            | 설명                                                              |
| ----------------- | ------------------------------------------------------------------------ |
| `PROCESS_RUNNING` | 프로세스가 정방향 실행을 통해 새로운 메모리 상태에 도달했습니다.            |
| `FLUSH_ALL`       | 프로세스의 메모리가 이전과 임의적으로 달라질 수 있습니다. |

## <a name="remarks"></a>주의

 디버거가 [ICorDebugProcess4::P rocessstatechanged](icordebugprocess4-processstatechanged-method.md) 또는 [ICorDebugProcess6::P rocessstatechanged](icordebugprocess6-processstatechanged-method.md) 를 사용 하 여 `ProcessStateChanged` 메서드를 호출할 때 `CorDebugStateChange` 열거형의 멤버가 인수로 제공 됩니다.

## <a name="requirements"></a>요구 사항

 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.

 **헤더:** CorDebug.idl, CorDebug.h

 **라이브러리:** CorGuids.lib

 **.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>참조

- [디버깅 열거형](debugging-enumerations.md)
- [디버깅](index.md)
