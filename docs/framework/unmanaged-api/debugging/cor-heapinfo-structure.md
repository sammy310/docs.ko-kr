---
title: COR_HEAPINFO 구조체
ms.date: 03/30/2017
api_name:
- COR_HEAPINFO
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_HEAPINFO
helpviewer_keywords:
- COR_HEAPINFO structure [.NET Framework debugging]
ms.assetid: bfb2cd39-3e0b-4d51-ba0c-f009755c1456
topic_type:
- apiref
ms.openlocfilehash: 37659262695b63a6dd6390c62c4bb7e04fdadca4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179305"
---
# <a name="cor_heapinfo-structure"></a><span data-ttu-id="29ef4-102">COR_HEAPINFO 구조체</span><span class="sxs-lookup"><span data-stu-id="29ef4-102">COR_HEAPINFO Structure</span></span>
<span data-ttu-id="29ef4-103">가비지 수집 힙에 대한 일반 정보(열거 가능 여부 포함)를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="29ef4-103">Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29ef4-104">구문</span><span class="sxs-lookup"><span data-stu-id="29ef4-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_HEAPINFO {  
    BOOL areGCStructuresValid;
    DWORD pointerSize;
    DWORD numHeaps;  
    BOOL concurrent;
    CorDebugGCType gcType;
} COR_HEAPINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="29ef4-105">구성원</span><span class="sxs-lookup"><span data-stu-id="29ef4-105">Members</span></span>  
  
|<span data-ttu-id="29ef4-106">멤버</span><span class="sxs-lookup"><span data-stu-id="29ef4-106">Member</span></span>|<span data-ttu-id="29ef4-107">Description</span><span class="sxs-lookup"><span data-stu-id="29ef4-107">Description</span></span>|  
|------------|-----------------|  
|`areGCStructuresValid`|<span data-ttu-id="29ef4-108">`true`가비지 수집 구조가 유효하고 힙을 열거할 수 있는 경우 그렇지 `false`않으면 .</span><span class="sxs-lookup"><span data-stu-id="29ef4-108">`true` if garbage collection structures are valid and the heap can be enumerated; otherwise, `false`.</span></span>|  
|`pointerSize`|<span data-ttu-id="29ef4-109">대상 아키텍처에 대한 포인터의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="29ef4-109">The size, in bytes, of pointers on the target architecture.</span></span>|  
|`numHeaps`|<span data-ttu-id="29ef4-110">프로세스의 논리 가비지 수집 힙 수입니다.</span><span class="sxs-lookup"><span data-stu-id="29ef4-110">The number of logical garbage collection heaps in the process.</span></span>|  
|`concurrent`|<span data-ttu-id="29ef4-111">`TRUE`동시(백그라운드) 가비지 수집이 활성화된 경우 그렇지 `FALSE`않으면 .</span><span class="sxs-lookup"><span data-stu-id="29ef4-111">`TRUE` if concurrent (background) garbage collection is enabled; otherwise, `FALSE`.</span></span>|  
|`gcType`|<span data-ttu-id="29ef4-112">가비지 수집기또는 서버에서 실행 중인지 여부를 나타내는 [CorDebugGCType](cordebuggctype-enumeration.md) 열거형의 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="29ef4-112">A member of the [CorDebugGCType](cordebuggctype-enumeration.md) enumeration that indicates whether the garbage collector is running on a workstation or a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29ef4-113">설명</span><span class="sxs-lookup"><span data-stu-id="29ef4-113">Remarks</span></span>  
 <span data-ttu-id="29ef4-114">`COR_HEAPINFO` 구조의 인스턴스는 [ICorDebugProcess5:GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) 메서드를 호출 하여 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29ef4-114">An instance of the `COR_HEAPINFO` structure is returned by calling the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
 <span data-ttu-id="29ef4-115">가비지 수집 힙의 개체를 열거하기 전에 `areGCStructuresValid` 항상 필드를 확인하여 힙이 열거 가능한 상태인지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29ef4-115">Before enumerating objects on the garbage collection heap, you must always check the `areGCStructuresValid` field to ensure that the heap is in an enumerable state.</span></span> <span data-ttu-id="29ef4-116">자세한 내용은 [ICorDebugProcess5:GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) 메서드를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="29ef4-116">For more information, see the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29ef4-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="29ef4-117">Requirements</span></span>  
 <span data-ttu-id="29ef4-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="29ef4-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29ef4-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="29ef4-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="29ef4-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29ef4-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29ef4-121">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29ef4-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29ef4-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="29ef4-122">See also</span></span>

- [<span data-ttu-id="29ef4-123">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="29ef4-123">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="29ef4-124">디버깅</span><span class="sxs-lookup"><span data-stu-id="29ef4-124">Debugging</span></span>](index.md)
