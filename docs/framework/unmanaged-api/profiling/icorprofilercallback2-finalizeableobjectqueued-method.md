---
title: ICorProfilerCallback2::FinalizeableObjectQueued 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.FinalizeableObjectQueued
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::FinalizeableObjectQueued
helpviewer_keywords:
- FinalizeableObjectQueued method [.NET Framework profiling]
- ICorProfilerCallback2::FinalizeableObjectQueued method [.NET Framework profiling]
ms.assetid: 92d76893-683c-475d-9996-5bff03cdb10f
topic_type:
- apiref
ms.openlocfilehash: ade0ba0517e47e9500683836b87d7a8ac1dfcfdb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439856"
---
# <a name="icorprofilercallback2finalizeableobjectqueued-method"></a><span data-ttu-id="a8ee5-102">ICorProfilerCallback2::FinalizeableObjectQueued 메서드</span><span class="sxs-lookup"><span data-stu-id="a8ee5-102">ICorProfilerCallback2::FinalizeableObjectQueued Method</span></span>
<span data-ttu-id="a8ee5-103">Notifies the code profiler that an object with a finalizer has been queued to the finalizer thread for execution of its `Finalize` method.</span><span class="sxs-lookup"><span data-stu-id="a8ee5-103">Notifies the code profiler that an object with a finalizer has been queued to the finalizer thread for execution of its `Finalize` method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8ee5-104">구문</span><span class="sxs-lookup"><span data-stu-id="a8ee5-104">Syntax</span></span>  
  
```cpp  
HRESULT FinalizeableObjectQueued(  
    [in] DWORD finalizerFlags,  
    [in] ObjectID objectID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8ee5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a8ee5-105">Parameters</span></span>  
 `finalizerFlags`  
 <span data-ttu-id="a8ee5-106">[in] A value of the [COR_PRF_FINALIZER_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-finalizer-flags-enumeration.md) enumeration that describes aspects of the finalizer.</span><span class="sxs-lookup"><span data-stu-id="a8ee5-106">[in] A value of the [COR_PRF_FINALIZER_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-finalizer-flags-enumeration.md) enumeration that describes aspects of the finalizer.</span></span>  
  
 `objectID`  
 <span data-ttu-id="a8ee5-107">[in] The ID of the object that has been queued.</span><span class="sxs-lookup"><span data-stu-id="a8ee5-107">[in] The ID of the object that has been queued.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8ee5-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a8ee5-108">Requirements</span></span>  
 <span data-ttu-id="a8ee5-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a8ee5-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8ee5-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a8ee5-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a8ee5-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8ee5-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8ee5-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8ee5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8ee5-113">참조</span><span class="sxs-lookup"><span data-stu-id="a8ee5-113">See also</span></span>

- [<span data-ttu-id="a8ee5-114">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a8ee5-114">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="a8ee5-115">ICorProfilerCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a8ee5-115">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
