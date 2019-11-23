---
title: ICorProfilerCallback2::GarbageCollectionFinished 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.GarbageCollectionFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::GarbageCollectionFinished
helpviewer_keywords:
- ICorProfilerCallback2::GarbageCollectionFinished method [.NET Framework profiling]
- GarbageCollectionFinished method [.NET Framework profiling]
ms.assetid: 1a5758ea-2354-43c0-92a3-32c9909d64e1
topic_type:
- apiref
ms.openlocfilehash: 1217bb30be8b88f8ba1cf21f03f2531778358d4b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439849"
---
# <a name="icorprofilercallback2garbagecollectionfinished-method"></a><span data-ttu-id="027a3-102">ICorProfilerCallback2::GarbageCollectionFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="027a3-102">ICorProfilerCallback2::GarbageCollectionFinished Method</span></span>
<span data-ttu-id="027a3-103">Notifies the profiler that garbage collection has completed and all garbage collection callbacks have been issued for it.</span><span class="sxs-lookup"><span data-stu-id="027a3-103">Notifies the profiler that garbage collection has completed and all garbage collection callbacks have been issued for it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="027a3-104">구문</span><span class="sxs-lookup"><span data-stu-id="027a3-104">Syntax</span></span>  
  
```cpp  
HRESULT GarbageCollectionFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="027a3-105">주의</span><span class="sxs-lookup"><span data-stu-id="027a3-105">Remarks</span></span>  
 <span data-ttu-id="027a3-106">It is safe for the profiler to inspect objects in their final locations when the `GarbageCollectionFinished` method is called.</span><span class="sxs-lookup"><span data-stu-id="027a3-106">It is safe for the profiler to inspect objects in their final locations when the `GarbageCollectionFinished` method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="027a3-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="027a3-107">Requirements</span></span>  
 <span data-ttu-id="027a3-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="027a3-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="027a3-109">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="027a3-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="027a3-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="027a3-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="027a3-111">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="027a3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="027a3-112">참조</span><span class="sxs-lookup"><span data-stu-id="027a3-112">See also</span></span>

- [<span data-ttu-id="027a3-113">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="027a3-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="027a3-114">ICorProfilerCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="027a3-114">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
