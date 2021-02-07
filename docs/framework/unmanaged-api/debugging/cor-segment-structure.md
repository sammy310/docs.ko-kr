---
description: '다음에 대 한 자세한 정보: COR_SEGMENT 구조체'
title: COR_SEGMENT 구조체
ms.date: 03/30/2017
api_name:
- COR_SEGMENT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_SEGMENT
helpviewer_keywords:
- COR_SEGMENT structure [.NET Framework debugging]
ms.assetid: 93aeecb9-7fef-4545-8daf-f566dfc47084
topic_type:
- apiref
ms.openlocfilehash: 9bbc452b2c2036d019175ac1be8b9917ffa07b6a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712188"
---
# <a name="cor_segment-structure"></a><span data-ttu-id="8eadf-103">COR_SEGMENT 구조체</span><span class="sxs-lookup"><span data-stu-id="8eadf-103">COR_SEGMENT Structure</span></span>

<span data-ttu-id="8eadf-104">관리되는 힙의 메모리 영역에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8eadf-104">Contains information about a region of memory in the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8eadf-105">구문</span><span class="sxs-lookup"><span data-stu-id="8eadf-105">Syntax</span></span>  
  
```cpp  
typedef struct _COR_SEGMENT {  
    CORDB_ADDRESS start;
    CORDB_ADDRESS end;
    CorDebugGenerationTypes gen;
    ULONG heap;
} COR_SEGMENT;  
```  
  
## <a name="members"></a><span data-ttu-id="8eadf-106">구성원</span><span class="sxs-lookup"><span data-stu-id="8eadf-106">Members</span></span>  
  
|<span data-ttu-id="8eadf-107">멤버</span><span class="sxs-lookup"><span data-stu-id="8eadf-107">Member</span></span>|<span data-ttu-id="8eadf-108">설명</span><span class="sxs-lookup"><span data-stu-id="8eadf-108">Description</span></span>|  
|------------|-----------------|  
|`start`|<span data-ttu-id="8eadf-109">메모리 영역의 시작 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="8eadf-109">The starting address of the memory region.</span></span>|  
|`end`|<span data-ttu-id="8eadf-110">메모리 영역의 끝 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="8eadf-110">The ending address of the memory region.</span></span>|  
|`gen`|<span data-ttu-id="8eadf-111">메모리 영역의 생성을 나타내는 [CorDebugGenerationTypes](cordebuggenerationtypes-enumeration.md) 열거형 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="8eadf-111">A [CorDebugGenerationTypes](cordebuggenerationtypes-enumeration.md) enumeration member that indicates the generation of the memory region.</span></span>|  
|`heap`|<span data-ttu-id="8eadf-112">메모리 영역이 있는 힙 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="8eadf-112">The heap number in which the memory region resides.</span></span> <span data-ttu-id="8eadf-113">자세한 내용은 설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8eadf-113">See the Remarks section for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8eadf-114">설명</span><span class="sxs-lookup"><span data-stu-id="8eadf-114">Remarks</span></span>  

 <span data-ttu-id="8eadf-115">`COR_SEGMENTS` 구조는 관리되는 힙의 메모리 영역을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8eadf-115">The `COR_SEGMENTS` structure represents a region of memory in the managed heap.</span></span>  <span data-ttu-id="8eadf-116">`COR_SEGMENTS` 개체는 [ICorDebugHeapRegionEnum](icordebugheapsegmentenum-interface.md) 컬렉션 개체의 멤버이며, [ICorDebugProcess5::EnumerateHeapRegions](icordebugprocess5-enumerateheapregions-method.md) 메서드를 호출하여 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="8eadf-116">`COR_SEGMENTS` objects are members of the [ICorDebugHeapRegionEnum](icordebugheapsegmentenum-interface.md) collection object, which is populated by calling the [ICorDebugProcess5::EnumerateHeapRegions](icordebugprocess5-enumerateheapregions-method.md) method.</span></span>  
  
 <span data-ttu-id="8eadf-117">`heap` 필드는 보고되는 힙에 해당하는 프로세서 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="8eadf-117">The `heap` field is the processor number, which corresponds to the heap being reported.</span></span> <span data-ttu-id="8eadf-118">워크스테이션 가비지 수집기의 경우 워크스테이션에 가비지 수집 힙이 하나만 있으므로, 해당 값은 항상 0입니다.</span><span class="sxs-lookup"><span data-stu-id="8eadf-118">For workstation garbage collectors, its value is always zero, because workstations have only one garbage collection heap.</span></span> <span data-ttu-id="8eadf-119">서버 가비지 수집기의 값은 힙이 연결된 프로세서에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="8eadf-119">For server garbage collectors, its value corresponds to the processor the heap is attached to.</span></span> <span data-ttu-id="8eadf-120">가비지 수집기의 구현 세부 정보로 인해 실제 프로세서보다 가비지 수집 힙이 더 많거나 적을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8eadf-120">Note that there may be more or fewer garbage collection heaps than there are actual processors due to the implementation details of the garbage collector.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8eadf-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8eadf-121">Requirements</span></span>  

 <span data-ttu-id="8eadf-122">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8eadf-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8eadf-123">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8eadf-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8eadf-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8eadf-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8eadf-125">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8eadf-125">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8eadf-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8eadf-126">See also</span></span>

- [<span data-ttu-id="8eadf-127">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="8eadf-127">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="8eadf-128">디버깅</span><span class="sxs-lookup"><span data-stu-id="8eadf-128">Debugging</span></span>](index.md)
