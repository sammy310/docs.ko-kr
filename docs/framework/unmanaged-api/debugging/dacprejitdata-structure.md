---
description: '자세히 알아보기: DacpReJitData Structure'
title: DacpReJitData 구조체
ms.date: 02/01/2019
api.name:
- DacpReJitData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpReJitData Structure
helpviewer.keywords:
- DacpReJitData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 8e8d506856dbc6579ac6ea0eee2b2088a980a315
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801438"
---
# <a name="dacprejitdata-structure"></a><span data-ttu-id="8a140-103">DacpReJitData 구조체</span><span class="sxs-lookup"><span data-stu-id="8a140-103">DacpReJitData Structure</span></span>

<span data-ttu-id="8a140-104">지정 된 프로파일러 계측 된 메서드에 대 한 기본 정보를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a140-104">Defines the basic information about a given profiler-instrumented method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="8a140-105">구문</span><span class="sxs-lookup"><span data-stu-id="8a140-105">Syntax</span></span>

```cpp
struct MSLAYOUT DacpReJitData
{
    enum Flags
    {
        kUnknown,
        kRequested,
        kActive,
        kReverted,
    };

    CLRDATA_ADDRESS                 rejitID;
    Flags                           flags;
    CLRDATA_ADDRESS                 NativeCodeAddr;
};
```

## <a name="members"></a><span data-ttu-id="8a140-106">구성원</span><span class="sxs-lookup"><span data-stu-id="8a140-106">Members</span></span>

| <span data-ttu-id="8a140-107">멤버</span><span class="sxs-lookup"><span data-stu-id="8a140-107">Member</span></span>           | <span data-ttu-id="8a140-108">설명</span><span class="sxs-lookup"><span data-stu-id="8a140-108">Description</span></span>                                                                                      |
| ---------------- | ------------------------------------------------------------------------------------------------ |
| `rejitID`        | <span data-ttu-id="8a140-109">메서드의 ReJit 수정 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="8a140-109">The ReJit revision number for a method.</span></span>                                                          |
| `flags`          | <span data-ttu-id="8a140-110">지정 된 버전에 대 한 메서드 ReJit 계측의 현재 상태를 나타내는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="8a140-110">A flag indicating the current state of the method's ReJit instrumentation for the given version.</span></span> |
| `NativeCodeAddr` | <span data-ttu-id="8a140-111">메서드의 rejitted 구현에 대 한 기본 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="8a140-111">The base address of the method's rejitted implementation.</span></span>                                         |

## <a name="remarks"></a><span data-ttu-id="8a140-112">설명</span><span class="sxs-lookup"><span data-stu-id="8a140-112">Remarks</span></span>

<span data-ttu-id="8a140-113">이 구조체는 런타임 내에 있으며 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a140-113">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="8a140-114">이를 사용 하려면 위에 지정 된 대로 구조를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a140-114">To use it, define the structure as specified above.</span></span> <span data-ttu-id="8a140-115">`ms_struct`Microsoft 컴파일러를 사용 하지 않는 경우에는 압축을 사용 하 여 구조도 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a140-115">The structure must also be defined using `ms_struct` packing if not using the Microsoft compilers.</span></span>

## <a name="requirements"></a><span data-ttu-id="8a140-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8a140-116">Requirements</span></span>

<span data-ttu-id="8a140-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8a140-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="8a140-118">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="8a140-118">**Header:** None</span></span>  
<span data-ttu-id="8a140-119">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="8a140-119">**Library:** None</span></span>  
<span data-ttu-id="8a140-120">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8a140-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="8a140-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8a140-121">See also</span></span>

- [<span data-ttu-id="8a140-122">디버깅</span><span class="sxs-lookup"><span data-stu-id="8a140-122">Debugging</span></span>](index.md)
- [<span data-ttu-id="8a140-123">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="8a140-123">Debugging Structures</span></span>](debugging-structures.md)
