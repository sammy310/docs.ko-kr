---
title: ICorProfilerInfo4::InitializeCurrentThread 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4::InitializeCurrentThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::InitializeCurrentThread
helpviewer_keywords:
- ICorProfilerInfo4::InitializeCurrentThread method [.NET Framework profiling]
- InitializeCurrentThread method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 18a3335c-8c75-476c-b6de-72c0bfedae5d
topic_type:
- apiref
ms.openlocfilehash: 39882a554f9d47040bef00ff320d15b56abea533
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445721"
---
# <a name="icorprofilerinfo4initializecurrentthread-method"></a><span data-ttu-id="70bad-102">ICorProfilerInfo4::InitializeCurrentThread 메서드</span><span class="sxs-lookup"><span data-stu-id="70bad-102">ICorProfilerInfo4::InitializeCurrentThread Method</span></span>
<span data-ttu-id="70bad-103">Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.</span><span class="sxs-lookup"><span data-stu-id="70bad-103">Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70bad-104">구문</span><span class="sxs-lookup"><span data-stu-id="70bad-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeCurrentThread ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="70bad-105">주의</span><span class="sxs-lookup"><span data-stu-id="70bad-105">Remarks</span></span>  
 <span data-ttu-id="70bad-106">We recommend that you call `InitializeCurrentThread` on any thread that will call a profiler API while there are suspended threads.</span><span class="sxs-lookup"><span data-stu-id="70bad-106">We recommend that you call `InitializeCurrentThread` on any thread that will call a profiler API while there are suspended threads.</span></span> <span data-ttu-id="70bad-107">This method is typically used by sampling profilers that create their own thread to call the [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method to perform stack walks while the target thread is suspended.</span><span class="sxs-lookup"><span data-stu-id="70bad-107">This method is typically used by sampling profilers that create their own thread to call the [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method to perform stack walks while the target thread is suspended.</span></span> <span data-ttu-id="70bad-108">By calling `InitializeCurrentThread` once when the profiler first creates the sampling thread, profilers can ensure that lazy per-thread initialization that the CLR would otherwise perform during the first call to `DoStackSnapshot` can now occur safely when no other threads are suspended.</span><span class="sxs-lookup"><span data-stu-id="70bad-108">By calling `InitializeCurrentThread` once when the profiler first creates the sampling thread, profilers can ensure that lazy per-thread initialization that the CLR would otherwise perform during the first call to `DoStackSnapshot` can now occur safely when no other threads are suspended.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="70bad-109">`InitializeCurrentThread` does the initialization in advance to finish tasks that take locks, and may deadlock.</span><span class="sxs-lookup"><span data-stu-id="70bad-109">`InitializeCurrentThread` does the initialization in advance to finish tasks that take locks, and may deadlock.</span></span> <span data-ttu-id="70bad-110">Call `InitializeCurrentThread` only when there are no suspended threads.</span><span class="sxs-lookup"><span data-stu-id="70bad-110">Call `InitializeCurrentThread` only when there are no suspended threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70bad-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="70bad-111">Requirements</span></span>  
 <span data-ttu-id="70bad-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70bad-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70bad-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="70bad-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="70bad-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70bad-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="70bad-115">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70bad-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70bad-116">참조</span><span class="sxs-lookup"><span data-stu-id="70bad-116">See also</span></span>

- [<span data-ttu-id="70bad-117">ICorProfilerInfo4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="70bad-117">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="70bad-118">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="70bad-118">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="70bad-119">프로파일링</span><span class="sxs-lookup"><span data-stu-id="70bad-119">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
