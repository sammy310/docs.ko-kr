---
description: '다음에 대 한 자세한 정보: 열거형 COR_PRF_GC_ROOT_FLAGS'
title: COR_PRF_GC_ROOT_FLAGS 열거형
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_ROOT_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_ROOT_FLAGS
helpviewer_keywords:
- COR_PRF_GC_ROOT_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 4611ee6f-0f05-4d84-91e1-e83d5e7dd7e4
topic_type:
- apiref
ms.openlocfilehash: 6d566ed5ac1d0b4e15a855fbbb8a0fca3a5a429e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99648820"
---
# <a name="cor_prf_gc_root_flags-enumeration"></a><span data-ttu-id="71ff8-103">COR_PRF_GC_ROOT_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="71ff8-103">COR_PRF_GC_ROOT_FLAGS Enumeration</span></span>

<span data-ttu-id="71ff8-104">가비지 컬렉션 루트의 속성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="71ff8-104">Indicates a property of a garbage collection root.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71ff8-105">구문</span><span class="sxs-lookup"><span data-stu-id="71ff8-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_ROOT_PINNING = 0x1,  
    COR_PRF_GC_ROOT_WEAKREF = 0x2,  
    COR_PRF_GC_ROOT_INTERIOR = 0x4,  
    COR_PRF_GC_ROOT_REFCOUNTED = 0x8,  
} COR_PRF_GC_ROOT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="71ff8-106">구성원</span><span class="sxs-lookup"><span data-stu-id="71ff8-106">Members</span></span>  
  
|<span data-ttu-id="71ff8-107">멤버</span><span class="sxs-lookup"><span data-stu-id="71ff8-107">Member</span></span>|<span data-ttu-id="71ff8-108">설명</span><span class="sxs-lookup"><span data-stu-id="71ff8-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_PINNING`|<span data-ttu-id="71ff8-109">Root를 설정 하면 가비지 수집에서 개체를 이동할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71ff8-109">The root prevents a garbage collection from moving the object.</span></span>|  
|`COR_PRF_GC_ROOT_WEAKREF`|<span data-ttu-id="71ff8-110">루트는 가비지 수집을 방지 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71ff8-110">The root does not prevent garbage collection.</span></span>|  
|`COR_PRF_GC_ROOT_INTERIOR`|<span data-ttu-id="71ff8-111">루트는 개체 자체가 아니라 개체의 필드를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="71ff8-111">The root refers to a field of the object rather than the object itself.</span></span>|  
|`COR_PRF_GC_ROOT_REFCOUNTED`|<span data-ttu-id="71ff8-112">개체의 참조 횟수가 특정 값 이면 루트는 가비지 수집을 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="71ff8-112">The root prevents garbage collection if the reference count of the object is a certain value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71ff8-113">설명</span><span class="sxs-lookup"><span data-stu-id="71ff8-113">Remarks</span></span>  

 <span data-ttu-id="71ff8-114">`COR_PRF_GC_ROOT_FLAGS` 는 특정 루트에 대 한 추가 정보를 제공 하는 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="71ff8-114">`COR_PRF_GC_ROOT_FLAGS` is a bitmask that provides additional information about special roots.</span></span> <span data-ttu-id="71ff8-115">그러나 모든 루트가 특수 한 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="71ff8-115">However, not all roots are special.</span></span> <span data-ttu-id="71ff8-116">예를 들어 일부 루트는 약한 참조, 내부 포인터, 고정 또는 참조 횟수가 계산 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71ff8-116">For example, some roots are not weak references, interior pointers, pinned, or reference-counted.</span></span> <span data-ttu-id="71ff8-117">이러한 루트의 경우 전달할 플래그가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71ff8-117">For such roots, there are no flags to convey.</span></span> <span data-ttu-id="71ff8-118">따라서 [ICorProfilerCallback2:: RootReferences2](icorprofilercallback2-rootreferences2-method.md) 메서드와 같이이 열거형을 사용 하는 메서드는 플래그 비트 마스크에 대해 0을 보내 모든 플래그가 해제 되어 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="71ff8-118">Therefore, methods that use this enumeration, such as the [ICorProfilerCallback2::RootReferences2](icorprofilercallback2-rootreferences2-method.md) method, send 0 for the flags bitmask, indicating that all flags are turned off.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71ff8-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="71ff8-119">Requirements</span></span>  

 <span data-ttu-id="71ff8-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="71ff8-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71ff8-121">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="71ff8-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="71ff8-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71ff8-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71ff8-123">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71ff8-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71ff8-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="71ff8-124">See also</span></span>

- [<span data-ttu-id="71ff8-125">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="71ff8-125">Profiling Enumerations</span></span>](profiling-enumerations.md)
