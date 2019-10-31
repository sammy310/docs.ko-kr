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
# <a name="cordebugstatechange-enumeration"></a><span data-ttu-id="7ebf1-102">CorDebugStateChange 열거형</span><span class="sxs-lookup"><span data-stu-id="7ebf1-102">CorDebugStateChange Enumeration</span></span>

<span data-ttu-id="7ebf1-103">프로세스에 대한 변경 내용을 기반으로 삭제해야 하는 캐시된 데이터의 양을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7ebf1-103">Describes the amount of cached data that must be discarded based on changes to the process.</span></span>

## <a name="syntax"></a><span data-ttu-id="7ebf1-104">구문</span><span class="sxs-lookup"><span data-stu-id="7ebf1-104">Syntax</span></span>

```cpp
typedef enum CorDebugStateChange
{
    PROCESS_RUNNING = 0x0000001,
    FLUSH_ALL       = 0x0000002,
} CorDebugStateChange;
```

## <a name="members"></a><span data-ttu-id="7ebf1-105">멤버</span><span class="sxs-lookup"><span data-stu-id="7ebf1-105">Members</span></span>

| <span data-ttu-id="7ebf1-106">멤버</span><span class="sxs-lookup"><span data-stu-id="7ebf1-106">Member</span></span>            | <span data-ttu-id="7ebf1-107">설명</span><span class="sxs-lookup"><span data-stu-id="7ebf1-107">Description</span></span>                                                              |
| ----------------- | ------------------------------------------------------------------------ |
| `PROCESS_RUNNING` | <span data-ttu-id="7ebf1-108">프로세스가 정방향 실행을 통해 새로운 메모리 상태에 도달했습니다.</span><span class="sxs-lookup"><span data-stu-id="7ebf1-108">The process reached a new memory state via forward execution.</span></span>            |
| `FLUSH_ALL`       | <span data-ttu-id="7ebf1-109">프로세스의 메모리가 이전과 임의적으로 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ebf1-109">The process' memory may be arbitrarily different than it was previously.</span></span> |

## <a name="remarks"></a><span data-ttu-id="7ebf1-110">주의</span><span class="sxs-lookup"><span data-stu-id="7ebf1-110">Remarks</span></span>

 <span data-ttu-id="7ebf1-111">디버거가 [ICorDebugProcess4::P rocessstatechanged](icordebugprocess4-processstatechanged-method.md) 또는 [ICorDebugProcess6::P rocessstatechanged](icordebugprocess6-processstatechanged-method.md) 를 사용 하 여 `ProcessStateChanged` 메서드를 호출할 때 `CorDebugStateChange` 열거형의 멤버가 인수로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ebf1-111">A member of the `CorDebugStateChange` enumeration is provided as an argument when the debugger calls the `ProcessStateChanged` method either with [ICorDebugProcess4::ProcessStateChanged](icordebugprocess4-processstatechanged-method.md) or [ICorDebugProcess6::ProcessStateChanged](icordebugprocess6-processstatechanged-method.md)</span></span>

## <a name="requirements"></a><span data-ttu-id="7ebf1-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7ebf1-112">Requirements</span></span>

 <span data-ttu-id="7ebf1-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7ebf1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="7ebf1-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ebf1-114">**Header:** CorDebug.idl, CorDebug.h</span></span>

 <span data-ttu-id="7ebf1-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ebf1-115">**Library:** CorGuids.lib</span></span>

 <span data-ttu-id="7ebf1-116">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ebf1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="7ebf1-117">참조</span><span class="sxs-lookup"><span data-stu-id="7ebf1-117">See also</span></span>

- [<span data-ttu-id="7ebf1-118">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="7ebf1-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="7ebf1-119">디버깅</span><span class="sxs-lookup"><span data-stu-id="7ebf1-119">Debugging</span></span>](index.md)
