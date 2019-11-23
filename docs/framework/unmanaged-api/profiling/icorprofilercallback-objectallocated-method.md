---
title: ICorProfilerCallback::ObjectAllocated 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectAllocated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectAllocated
helpviewer_keywords:
- ObjectAllocated method [.NET Framework profiling]
- ICorProfilerCallback::ObjectAllocated method [.NET Framework profiling]
ms.assetid: eb412622-77cc-4abd-a2cd-c910fe8edd54
topic_type:
- apiref
ms.openlocfilehash: 66643bbb8dbc914b2e0e48a7f0c87630fe95e5d3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445845"
---
# <a name="icorprofilercallbackobjectallocated-method"></a><span data-ttu-id="a4cf3-102">ICorProfilerCallback::ObjectAllocated 메서드</span><span class="sxs-lookup"><span data-stu-id="a4cf3-102">ICorProfilerCallback::ObjectAllocated Method</span></span>
<span data-ttu-id="a4cf3-103">Notifies the profiler that memory within the heap has been allocated for an object.</span><span class="sxs-lookup"><span data-stu-id="a4cf3-103">Notifies the profiler that memory within the heap has been allocated for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4cf3-104">구문</span><span class="sxs-lookup"><span data-stu-id="a4cf3-104">Syntax</span></span>  
  
```cpp  
HRESULT ObjectAllocated(  
    [in] ObjectID objectId,  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4cf3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a4cf3-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="a4cf3-106">[in] The ID of the object for which memory was allocated.</span><span class="sxs-lookup"><span data-stu-id="a4cf3-106">[in] The ID of the object for which memory was allocated.</span></span>  
  
 `classId`  
 <span data-ttu-id="a4cf3-107">[in] The ID of the class of which the object is an instance.</span><span class="sxs-lookup"><span data-stu-id="a4cf3-107">[in] The ID of the class of which the object is an instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4cf3-108">주의</span><span class="sxs-lookup"><span data-stu-id="a4cf3-108">Remarks</span></span>  
 <span data-ttu-id="a4cf3-109">The `ObjectedAllocated` method is not called for allocations from either the stack or unmanaged memory.</span><span class="sxs-lookup"><span data-stu-id="a4cf3-109">The `ObjectedAllocated` method is not called for allocations from either the stack or unmanaged memory.</span></span> <span data-ttu-id="a4cf3-110">The `classId` parameter can refer to a class in managed code that has not been loaded yet.</span><span class="sxs-lookup"><span data-stu-id="a4cf3-110">The `classId` parameter can refer to a class in managed code that has not been loaded yet.</span></span> <span data-ttu-id="a4cf3-111">The profiler will receive a class load callback for that class immediately after the `ObjectAllocated` callback.</span><span class="sxs-lookup"><span data-stu-id="a4cf3-111">The profiler will receive a class load callback for that class immediately after the `ObjectAllocated` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4cf3-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a4cf3-112">Requirements</span></span>  
 <span data-ttu-id="a4cf3-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a4cf3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4cf3-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a4cf3-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a4cf3-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4cf3-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a4cf3-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4cf3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4cf3-117">참조</span><span class="sxs-lookup"><span data-stu-id="a4cf3-117">See also</span></span>

- [<span data-ttu-id="a4cf3-118">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a4cf3-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="a4cf3-119">ClassLoadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="a4cf3-119">ClassLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)
- [<span data-ttu-id="a4cf3-120">ClassLoadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="a4cf3-120">ClassLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)
