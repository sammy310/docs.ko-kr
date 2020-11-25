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
ms.openlocfilehash: 5400350e1c489ec4c2ff3cddf83a4f1a8a0c7947
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726602"
---
# <a name="cor_heapinfo-structure"></a><span data-ttu-id="cf66e-102">COR_HEAPINFO 구조체</span><span class="sxs-lookup"><span data-stu-id="cf66e-102">COR_HEAPINFO Structure</span></span>

<span data-ttu-id="cf66e-103">가비지 수집 힙에 대한 일반 정보(열거 가능 여부 포함)를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cf66e-103">Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf66e-104">구문</span><span class="sxs-lookup"><span data-stu-id="cf66e-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_HEAPINFO {  
    BOOL areGCStructuresValid;
    DWORD pointerSize;
    DWORD numHeaps;  
    BOOL concurrent;
    CorDebugGCType gcType;
} COR_HEAPINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="cf66e-105">멤버</span><span class="sxs-lookup"><span data-stu-id="cf66e-105">Members</span></span>  
  
|<span data-ttu-id="cf66e-106">멤버</span><span class="sxs-lookup"><span data-stu-id="cf66e-106">Member</span></span>|<span data-ttu-id="cf66e-107">설명</span><span class="sxs-lookup"><span data-stu-id="cf66e-107">Description</span></span>|  
|------------|-----------------|  
|`areGCStructuresValid`|<span data-ttu-id="cf66e-108">`true` 가비지 수집 구조가 올바르고 힙을 열거할 수 있으면이 고, 그렇지 않으면입니다. 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="cf66e-108">`true` if garbage collection structures are valid and the heap can be enumerated; otherwise, `false`.</span></span>|  
|`pointerSize`|<span data-ttu-id="cf66e-109">대상 아키텍처에 대 한 포인터의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="cf66e-109">The size, in bytes, of pointers on the target architecture.</span></span>|  
|`numHeaps`|<span data-ttu-id="cf66e-110">프로세스의 논리적 가비지 수집 힙 수입니다.</span><span class="sxs-lookup"><span data-stu-id="cf66e-110">The number of logical garbage collection heaps in the process.</span></span>|  
|`concurrent`|<span data-ttu-id="cf66e-111">`TRUE` 동시 (백그라운드) 가비지 수집을 사용 하는 경우 그렇지 않으면 `FALSE` 입니다.</span><span class="sxs-lookup"><span data-stu-id="cf66e-111">`TRUE` if concurrent (background) garbage collection is enabled; otherwise, `FALSE`.</span></span>|  
|`gcType`|<span data-ttu-id="cf66e-112">가비지 수집기가 워크스테이션 또는 서버에서 실행 중인지 여부를 나타내는 [CorDebugGCType](cordebuggctype-enumeration.md) 열거의 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="cf66e-112">A member of the [CorDebugGCType](cordebuggctype-enumeration.md) enumeration that indicates whether the garbage collector is running on a workstation or a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cf66e-113">설명</span><span class="sxs-lookup"><span data-stu-id="cf66e-113">Remarks</span></span>  

 <span data-ttu-id="cf66e-114">`COR_HEAPINFO` [ICorDebugProcess5:: GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) 메서드를 호출 하 여 구조체의 인스턴스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf66e-114">An instance of the `COR_HEAPINFO` structure is returned by calling the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
 <span data-ttu-id="cf66e-115">가비지 컬렉션 힙에서 개체를 열거 하기 전에 항상 필드를 확인 하 여 `areGCStructuresValid` 힙이 열거 가능한 상태 인지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf66e-115">Before enumerating objects on the garbage collection heap, you must always check the `areGCStructuresValid` field to ensure that the heap is in an enumerable state.</span></span> <span data-ttu-id="cf66e-116">자세한 내용은 [ICorDebugProcess5:: GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) 메서드를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cf66e-116">For more information, see the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf66e-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cf66e-117">Requirements</span></span>  

 <span data-ttu-id="cf66e-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cf66e-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf66e-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cf66e-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cf66e-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf66e-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf66e-121">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf66e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf66e-122">참조</span><span class="sxs-lookup"><span data-stu-id="cf66e-122">See also</span></span>

- [<span data-ttu-id="cf66e-123">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="cf66e-123">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="cf66e-124">디버깅</span><span class="sxs-lookup"><span data-stu-id="cf66e-124">Debugging</span></span>](index.md)
