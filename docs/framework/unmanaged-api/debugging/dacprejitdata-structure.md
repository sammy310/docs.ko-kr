---
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
ms.openlocfilehash: 4436ece72b0a6a405fc41cba5413093fc42ce750
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860772"
---
# <a name="dacprejitdata-structure"></a><span data-ttu-id="b7fe4-102">DacpReJitData 구조체</span><span class="sxs-lookup"><span data-stu-id="b7fe4-102">DacpReJitData Structure</span></span>

<span data-ttu-id="b7fe4-103">지정 된 프로파일러 계측 된 메서드에 대 한 기본 정보를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fe4-103">Defines the basic information about a given profiler-instrumented method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="b7fe4-104">구문</span><span class="sxs-lookup"><span data-stu-id="b7fe4-104">Syntax</span></span>

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

## <a name="members"></a><span data-ttu-id="b7fe4-105">구성원</span><span class="sxs-lookup"><span data-stu-id="b7fe4-105">Members</span></span>

| <span data-ttu-id="b7fe4-106">멤버</span><span class="sxs-lookup"><span data-stu-id="b7fe4-106">Member</span></span>           | <span data-ttu-id="b7fe4-107">Description</span><span class="sxs-lookup"><span data-stu-id="b7fe4-107">Description</span></span>                                                                                      |
| ---------------- | ------------------------------------------------------------------------------------------------ |
| `rejitID`        | <span data-ttu-id="b7fe4-108">메서드의 ReJit 수정 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="b7fe4-108">The ReJit revision number for a method.</span></span>                                                          |
| `flags`          | <span data-ttu-id="b7fe4-109">지정 된 버전에 대 한 메서드 ReJit 계측의 현재 상태를 나타내는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="b7fe4-109">A flag indicating the current state of the method's ReJit instrumentation for the given version.</span></span> |
| `NativeCodeAddr` | <span data-ttu-id="b7fe4-110">메서드의 rejitted 구현에 대 한 기본 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="b7fe4-110">The base address of the method's rejitted implementation.</span></span>                                         |

## <a name="remarks"></a><span data-ttu-id="b7fe4-111">설명</span><span class="sxs-lookup"><span data-stu-id="b7fe4-111">Remarks</span></span>

<span data-ttu-id="b7fe4-112">이 구조체는 런타임 내에 있으며 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7fe4-112">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="b7fe4-113">이를 사용 하려면 위에 지정 된 대로 구조를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fe4-113">To use it, define the structure as specified above.</span></span> <span data-ttu-id="b7fe4-114">Microsoft 컴파일러를 사용 하지 않는 경우 `ms_struct` 에는 압축을 사용 하 여 구조도 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fe4-114">The structure must also be defined using `ms_struct` packing if not using the Microsoft compilers.</span></span>

## <a name="requirements"></a><span data-ttu-id="b7fe4-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b7fe4-115">Requirements</span></span>
<span data-ttu-id="b7fe4-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b7fe4-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="b7fe4-117">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="b7fe4-117">**Header:** None</span></span>  
<span data-ttu-id="b7fe4-118">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="b7fe4-118">**Library:** None</span></span>  
<span data-ttu-id="b7fe4-119">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b7fe4-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="b7fe4-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b7fe4-120">See also</span></span>

- [<span data-ttu-id="b7fe4-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="b7fe4-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="b7fe4-122">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="b7fe4-122">Debugging Structures</span></span>](debugging-structures.md)
