---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: faf1be65d308b223490f3ae67eed3d8a2b1688b9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609366"
---
# <a name="corsegment-structure"></a><span data-ttu-id="94a32-102">COR_SEGMENT 구조체</span><span class="sxs-lookup"><span data-stu-id="94a32-102">COR_SEGMENT Structure</span></span>
<span data-ttu-id="94a32-103">관리되는 힙의 메모리 영역에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="94a32-103">Contains information about a region of memory in the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94a32-104">구문</span><span class="sxs-lookup"><span data-stu-id="94a32-104">Syntax</span></span>  
  
```  
typedef struct _COR_SEGMENT {  
    CORDB_ADDRESS start;            
    CORDB_ADDRESS end;              
    CorDebugGenerationTypes gen;    
    ULONG heap;                     
} COR_SEGMENT;  
```  
  
## <a name="members"></a><span data-ttu-id="94a32-105">멤버</span><span class="sxs-lookup"><span data-stu-id="94a32-105">Members</span></span>  
  
|<span data-ttu-id="94a32-106">멤버</span><span class="sxs-lookup"><span data-stu-id="94a32-106">Member</span></span>|<span data-ttu-id="94a32-107">설명</span><span class="sxs-lookup"><span data-stu-id="94a32-107">Description</span></span>|  
|------------|-----------------|  
|`start`|<span data-ttu-id="94a32-108">메모리 영역의 시작 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="94a32-108">The starting address of the memory region.</span></span>|  
|`end`|<span data-ttu-id="94a32-109">메모리 영역의 끝 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="94a32-109">The ending address of the memory region.</span></span>|  
|`gen`|<span data-ttu-id="94a32-110">메모리 영역의 생성을 나타내는 [CorDebugGenerationTypes](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md) 열거형 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="94a32-110">A [CorDebugGenerationTypes](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md) enumeration member that indicates the generation of the memory region.</span></span>|  
|`heap`|<span data-ttu-id="94a32-111">메모리 영역이 있는 힙 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="94a32-111">The heap number in which the memory region resides.</span></span> <span data-ttu-id="94a32-112">자세한 내용은 설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94a32-112">See the Remarks section for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94a32-113">설명</span><span class="sxs-lookup"><span data-stu-id="94a32-113">Remarks</span></span>  
 <span data-ttu-id="94a32-114">`COR_SEGMENTS` 구조는 관리되는 힙의 메모리 영역을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="94a32-114">The `COR_SEGMENTS` structure represents a region of memory in the managed heap.</span></span>  <span data-ttu-id="94a32-115">`COR_SEGMENTS` 개체는 [ICorDebugHeapRegionEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) 컬렉션 개체의 멤버이며, [ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) 메서드를 호출하여 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="94a32-115">`COR_SEGMENTS` objects are members of the [ICorDebugHeapRegionEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) collection object, which is populated by calling the [ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) method.</span></span>  
  
 <span data-ttu-id="94a32-116">`heap` 필드는 보고되는 힙에 해당하는 프로세서 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="94a32-116">The `heap` field is the processor number, which corresponds to the heap being reported.</span></span> <span data-ttu-id="94a32-117">워크스테이션 가비지 수집기의 경우 워크스테이션에 가비지 수집 힙이 하나만 있으므로, 해당 값은 항상 0입니다.</span><span class="sxs-lookup"><span data-stu-id="94a32-117">For workstation garbage collectors, its value is always zero, because workstations have only one garbage collection heap.</span></span> <span data-ttu-id="94a32-118">서버 가비지 수집기의 값은 힙이 연결된 프로세서에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="94a32-118">For server garbage collectors, its value corresponds to the processor the heap is attached to.</span></span> <span data-ttu-id="94a32-119">가비지 수집기의 구현 세부 정보로 인해 실제 프로세서보다 가비지 수집 힙이 더 많거나 적을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94a32-119">Note that there may be more or fewer garbage collection heaps than there are actual processors due to the implementation details of the garbage collector.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94a32-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="94a32-120">Requirements</span></span>  
 <span data-ttu-id="94a32-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="94a32-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94a32-122">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="94a32-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="94a32-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94a32-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94a32-124">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94a32-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94a32-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="94a32-125">See also</span></span>

- [<span data-ttu-id="94a32-126">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="94a32-126">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="94a32-127">디버깅</span><span class="sxs-lookup"><span data-stu-id="94a32-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
