---
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
ms.openlocfilehash: 0210aca5698cd9c86979c13afd1e622b50d194df
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867188"
---
# <a name="cor_prf_gc_root_flags-enumeration"></a><span data-ttu-id="52c41-102">COR_PRF_GC_ROOT_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="52c41-102">COR_PRF_GC_ROOT_FLAGS Enumeration</span></span>
<span data-ttu-id="52c41-103">가비지 컬렉션 루트의 속성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="52c41-103">Indicates a property of a garbage collection root.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52c41-104">구문</span><span class="sxs-lookup"><span data-stu-id="52c41-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_ROOT_PINNING = 0x1,  
    COR_PRF_GC_ROOT_WEAKREF = 0x2,  
    COR_PRF_GC_ROOT_INTERIOR = 0x4,  
    COR_PRF_GC_ROOT_REFCOUNTED = 0x8,  
} COR_PRF_GC_ROOT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="52c41-105">Members</span><span class="sxs-lookup"><span data-stu-id="52c41-105">Members</span></span>  
  
|<span data-ttu-id="52c41-106">Member</span><span class="sxs-lookup"><span data-stu-id="52c41-106">Member</span></span>|<span data-ttu-id="52c41-107">설명</span><span class="sxs-lookup"><span data-stu-id="52c41-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_PINNING`|<span data-ttu-id="52c41-108">Root를 설정 하면 가비지 수집에서 개체를 이동할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="52c41-108">The root prevents a garbage collection from moving the object.</span></span>|  
|`COR_PRF_GC_ROOT_WEAKREF`|<span data-ttu-id="52c41-109">루트는 가비지 수집을 방지 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="52c41-109">The root does not prevent garbage collection.</span></span>|  
|`COR_PRF_GC_ROOT_INTERIOR`|<span data-ttu-id="52c41-110">루트는 개체 자체가 아니라 개체의 필드를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="52c41-110">The root refers to a field of the object rather than the object itself.</span></span>|  
|`COR_PRF_GC_ROOT_REFCOUNTED`|<span data-ttu-id="52c41-111">개체의 참조 횟수가 특정 값 이면 루트는 가비지 수집을 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="52c41-111">The root prevents garbage collection if the reference count of the object is a certain value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52c41-112">주의</span><span class="sxs-lookup"><span data-stu-id="52c41-112">Remarks</span></span>  
 <span data-ttu-id="52c41-113">`COR_PRF_GC_ROOT_FLAGS`은 특정 루트에 대 한 추가 정보를 제공 하는 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="52c41-113">`COR_PRF_GC_ROOT_FLAGS` is a bitmask that provides additional information about special roots.</span></span> <span data-ttu-id="52c41-114">그러나 모든 루트가 특수 한 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="52c41-114">However, not all roots are special.</span></span> <span data-ttu-id="52c41-115">예를 들어 일부 루트는 약한 참조, 내부 포인터, 고정 또는 참조 횟수가 계산 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="52c41-115">For example, some roots are not weak references, interior pointers, pinned, or reference-counted.</span></span> <span data-ttu-id="52c41-116">이러한 루트의 경우 전달할 플래그가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="52c41-116">For such roots, there are no flags to convey.</span></span> <span data-ttu-id="52c41-117">따라서 [ICorProfilerCallback2:: RootReferences2](icorprofilercallback2-rootreferences2-method.md) 메서드와 같이이 열거형을 사용 하는 메서드는 플래그 비트 마스크에 대해 0을 보내 모든 플래그가 해제 되어 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="52c41-117">Therefore, methods that use this enumeration, such as the [ICorProfilerCallback2::RootReferences2](icorprofilercallback2-rootreferences2-method.md) method, send 0 for the flags bitmask, indicating that all flags are turned off.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52c41-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="52c41-118">Requirements</span></span>  
 <span data-ttu-id="52c41-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="52c41-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52c41-120">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="52c41-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="52c41-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52c41-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52c41-122">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52c41-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52c41-123">참조</span><span class="sxs-lookup"><span data-stu-id="52c41-123">See also</span></span>

- [<span data-ttu-id="52c41-124">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="52c41-124">Profiling Enumerations</span></span>](profiling-enumerations.md)
