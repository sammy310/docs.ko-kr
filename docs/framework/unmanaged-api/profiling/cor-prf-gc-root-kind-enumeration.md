---
title: COR_PRF_GC_ROOT_KIND 열거형
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_ROOT_KIND
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_ROOT_KIND
helpviewer_keywords:
- COR_PRF_GC_ROOT_KIND enumeration [.NET Framework profiling]
ms.assetid: b9fb1c03-417f-41d4-aed4-02cb4ade8def
topic_type:
- apiref
ms.openlocfilehash: 2fe4735b7f218e89577702cde04d8d4f4de2a971
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447359"
---
# <a name="cor_prf_gc_root_kind-enumeration"></a><span data-ttu-id="bfd1d-102">COR_PRF_GC_ROOT_KIND 열거형</span><span class="sxs-lookup"><span data-stu-id="bfd1d-102">COR_PRF_GC_ROOT_KIND Enumeration</span></span>
<span data-ttu-id="bfd1d-103">Indicates the kind of garbage collection root that is exposed by the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="bfd1d-103">Indicates the kind of garbage collection root that is exposed by the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfd1d-104">구문</span><span class="sxs-lookup"><span data-stu-id="bfd1d-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_ROOT_STACK = 1,  
    COR_PRF_GC_ROOT_FINALIZER = 2,  
    COR_PRF_GC_ROOT_HANDLE = 3,  
    COR_PRF_GC_ROOT_OTHER = 0  
} COR_PRF_GC_ROOT_KIND;  
```  
  
## <a name="members"></a><span data-ttu-id="bfd1d-105">멤버</span><span class="sxs-lookup"><span data-stu-id="bfd1d-105">Members</span></span>  
  
|<span data-ttu-id="bfd1d-106">멤버</span><span class="sxs-lookup"><span data-stu-id="bfd1d-106">Member</span></span>|<span data-ttu-id="bfd1d-107">설명</span><span class="sxs-lookup"><span data-stu-id="bfd1d-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_STACK`|<span data-ttu-id="bfd1d-108">The root is a variable on the stack.</span><span class="sxs-lookup"><span data-stu-id="bfd1d-108">The root is a variable on the stack.</span></span>|  
|`COR_PRF_GC_ROOT_FINALIZER`|<span data-ttu-id="bfd1d-109">The root is an entry in the finalizer queue.</span><span class="sxs-lookup"><span data-stu-id="bfd1d-109">The root is an entry in the finalizer queue.</span></span>|  
|`COR_PRF_GC_ROOT_HANDLE`|<span data-ttu-id="bfd1d-110">The root is a garbage collection handle.</span><span class="sxs-lookup"><span data-stu-id="bfd1d-110">The root is a garbage collection handle.</span></span>|  
|`COR_PRF_GC_ROOT_OTHER`|<span data-ttu-id="bfd1d-111">The kind of root is unspecified.</span><span class="sxs-lookup"><span data-stu-id="bfd1d-111">The kind of root is unspecified.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bfd1d-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bfd1d-112">Requirements</span></span>  
 <span data-ttu-id="bfd1d-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bfd1d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfd1d-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bfd1d-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bfd1d-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bfd1d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bfd1d-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfd1d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfd1d-117">참조</span><span class="sxs-lookup"><span data-stu-id="bfd1d-117">See also</span></span>

- [<span data-ttu-id="bfd1d-118">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="bfd1d-118">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
