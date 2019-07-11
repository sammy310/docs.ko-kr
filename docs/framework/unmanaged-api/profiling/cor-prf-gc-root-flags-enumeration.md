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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7f179e3b01d6c3b34dfa765565a0fc38d0ba867c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753690"
---
# <a name="corprfgcrootflags-enumeration"></a><span data-ttu-id="221ee-102">COR_PRF_GC_ROOT_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="221ee-102">COR_PRF_GC_ROOT_FLAGS Enumeration</span></span>
<span data-ttu-id="221ee-103">가비지 컬렉션 루트의 속성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="221ee-103">Indicates a property of a garbage collection root.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="221ee-104">구문</span><span class="sxs-lookup"><span data-stu-id="221ee-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_ROOT_PINNING = 0x1,  
    COR_PRF_GC_ROOT_WEAKREF = 0x2,  
    COR_PRF_GC_ROOT_INTERIOR = 0x4,  
    COR_PRF_GC_ROOT_REFCOUNTED = 0x8,  
} COR_PRF_GC_ROOT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="221ee-105">멤버</span><span class="sxs-lookup"><span data-stu-id="221ee-105">Members</span></span>  
  
|<span data-ttu-id="221ee-106">멤버</span><span class="sxs-lookup"><span data-stu-id="221ee-106">Member</span></span>|<span data-ttu-id="221ee-107">Description</span><span class="sxs-lookup"><span data-stu-id="221ee-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_PINNING`|<span data-ttu-id="221ee-108">루트 개체를 이동 가비지 수집을 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="221ee-108">The root prevents a garbage collection from moving the object.</span></span>|  
|`COR_PRF_GC_ROOT_WEAKREF`|<span data-ttu-id="221ee-109">루트는 가비지 수집을 방지 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="221ee-109">The root does not prevent garbage collection.</span></span>|  
|`COR_PRF_GC_ROOT_INTERIOR`|<span data-ttu-id="221ee-110">루트 개체 자체가 아니라 개체의 필드를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="221ee-110">The root refers to a field of the object rather than the object itself.</span></span>|  
|`COR_PRF_GC_ROOT_REFCOUNTED`|<span data-ttu-id="221ee-111">루트 개체의 참조 횟수 특정 값인 경우 가비지 수집을 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="221ee-111">The root prevents garbage collection if the reference count of the object is a certain value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="221ee-112">설명</span><span class="sxs-lookup"><span data-stu-id="221ee-112">Remarks</span></span>  
 <span data-ttu-id="221ee-113">`COR_PRF_GC_ROOT_FLAGS` 특별 한 루트에 대 한 추가 정보를 제공 하는 비트 마스크가입니다.</span><span class="sxs-lookup"><span data-stu-id="221ee-113">`COR_PRF_GC_ROOT_FLAGS` is a bitmask that provides additional information about special roots.</span></span> <span data-ttu-id="221ee-114">그러나 일부 루트는 특별 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="221ee-114">However, not all roots are special.</span></span> <span data-ttu-id="221ee-115">예를 들어, 일부 루트는 약한 참조를 내부 포인터, 고정 또는 참조 횟수가 계산 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="221ee-115">For example, some roots are not weak references, interior pointers, pinned, or reference-counted.</span></span> <span data-ttu-id="221ee-116">이러한 루트에 대 한 전달할 플래그가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="221ee-116">For such roots, there are no flags to convey.</span></span> <span data-ttu-id="221ee-117">따라서 같은이 열거형을 사용 하는 메서드를 [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) 메서드인 모든 플래그를 나타내는 플래그 비트 마스크에 대 한 send 0은 해제 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="221ee-117">Therefore, methods that use this enumeration, such as the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) method, send 0 for the flags bitmask, indicating that all flags are turned off.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="221ee-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="221ee-118">Requirements</span></span>  
 <span data-ttu-id="221ee-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="221ee-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="221ee-120">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="221ee-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="221ee-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="221ee-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="221ee-122">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="221ee-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="221ee-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="221ee-123">See also</span></span>

- [<span data-ttu-id="221ee-124">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="221ee-124">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
