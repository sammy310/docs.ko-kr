---
description: '다음에 대 한 자세한 정보: COR_HEAPINFO 구조체'
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
ms.openlocfilehash: 0841739172b3eaf807813af28e0b20fbb54608b2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712316"
---
# <a name="cor_heapinfo-structure"></a><span data-ttu-id="5971d-103">COR_HEAPINFO 구조체</span><span class="sxs-lookup"><span data-stu-id="5971d-103">COR_HEAPINFO Structure</span></span>

<span data-ttu-id="5971d-104">가비지 수집 힙에 대한 일반 정보(열거 가능 여부 포함)를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5971d-104">Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5971d-105">구문</span><span class="sxs-lookup"><span data-stu-id="5971d-105">Syntax</span></span>  
  
```cpp  
typedef struct _COR_HEAPINFO {  
    BOOL areGCStructuresValid;
    DWORD pointerSize;
    DWORD numHeaps;  
    BOOL concurrent;
    CorDebugGCType gcType;
} COR_HEAPINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="5971d-106">구성원</span><span class="sxs-lookup"><span data-stu-id="5971d-106">Members</span></span>  
  
|<span data-ttu-id="5971d-107">멤버</span><span class="sxs-lookup"><span data-stu-id="5971d-107">Member</span></span>|<span data-ttu-id="5971d-108">설명</span><span class="sxs-lookup"><span data-stu-id="5971d-108">Description</span></span>|  
|------------|-----------------|  
|`areGCStructuresValid`|<span data-ttu-id="5971d-109">`true` 가비지 수집 구조가 올바르고 힙을 열거할 수 있으면이 고, 그렇지 않으면입니다. 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="5971d-109">`true` if garbage collection structures are valid and the heap can be enumerated; otherwise, `false`.</span></span>|  
|`pointerSize`|<span data-ttu-id="5971d-110">대상 아키텍처에 대 한 포인터의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="5971d-110">The size, in bytes, of pointers on the target architecture.</span></span>|  
|`numHeaps`|<span data-ttu-id="5971d-111">프로세스의 논리적 가비지 수집 힙 수입니다.</span><span class="sxs-lookup"><span data-stu-id="5971d-111">The number of logical garbage collection heaps in the process.</span></span>|  
|`concurrent`|<span data-ttu-id="5971d-112">`TRUE` 동시 (백그라운드) 가비지 수집을 사용 하는 경우 그렇지 않으면 `FALSE` 입니다.</span><span class="sxs-lookup"><span data-stu-id="5971d-112">`TRUE` if concurrent (background) garbage collection is enabled; otherwise, `FALSE`.</span></span>|  
|`gcType`|<span data-ttu-id="5971d-113">가비지 수집기가 워크스테이션 또는 서버에서 실행 중인지 여부를 나타내는 [CorDebugGCType](cordebuggctype-enumeration.md) 열거의 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="5971d-113">A member of the [CorDebugGCType](cordebuggctype-enumeration.md) enumeration that indicates whether the garbage collector is running on a workstation or a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5971d-114">설명</span><span class="sxs-lookup"><span data-stu-id="5971d-114">Remarks</span></span>  

 <span data-ttu-id="5971d-115">`COR_HEAPINFO` [ICorDebugProcess5:: GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) 메서드를 호출 하 여 구조체의 인스턴스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5971d-115">An instance of the `COR_HEAPINFO` structure is returned by calling the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
 <span data-ttu-id="5971d-116">가비지 컬렉션 힙에서 개체를 열거 하기 전에 항상 필드를 확인 하 여 `areGCStructuresValid` 힙이 열거 가능한 상태 인지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5971d-116">Before enumerating objects on the garbage collection heap, you must always check the `areGCStructuresValid` field to ensure that the heap is in an enumerable state.</span></span> <span data-ttu-id="5971d-117">자세한 내용은 [ICorDebugProcess5:: GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) 메서드를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5971d-117">For more information, see the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5971d-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5971d-118">Requirements</span></span>  

 <span data-ttu-id="5971d-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5971d-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5971d-120">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5971d-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5971d-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5971d-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5971d-122">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5971d-122">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5971d-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5971d-123">See also</span></span>

- [<span data-ttu-id="5971d-124">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="5971d-124">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="5971d-125">디버깅</span><span class="sxs-lookup"><span data-stu-id="5971d-125">Debugging</span></span>](index.md)
