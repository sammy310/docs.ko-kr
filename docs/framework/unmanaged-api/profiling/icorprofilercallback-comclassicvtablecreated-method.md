---
title: ICorProfilerCallback::COMClassicVTableCreated 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.COMClassicVTableCreated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::COMClassicVTableCreated
helpviewer_keywords:
- COMClassicVTableCreated method [.NET Framework profiling]
- ICorProfilerCallback::COMClassicVTableCreated method [.NET Framework profiling]
ms.assetid: 6e1834ab-c359-498a-b10b-984ae23cdda4
topic_type:
- apiref
ms.openlocfilehash: 79be2572f52ec509d9551261074204bf62ad5388
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445054"
---
# <a name="icorprofilercallbackcomclassicvtablecreated-method"></a><span data-ttu-id="b3451-102">ICorProfilerCallback::COMClassicVTableCreated 메서드</span><span class="sxs-lookup"><span data-stu-id="b3451-102">ICorProfilerCallback::COMClassicVTableCreated Method</span></span>
<span data-ttu-id="b3451-103">Notifies the profiler that a COM interop vtable for the specified IID and class has been created.</span><span class="sxs-lookup"><span data-stu-id="b3451-103">Notifies the profiler that a COM interop vtable for the specified IID and class has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3451-104">구문</span><span class="sxs-lookup"><span data-stu-id="b3451-104">Syntax</span></span>  
  
```cpp  
HRESULT COMClassicVTableCreated(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable,  
    [in] ULONG   cSlots);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3451-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b3451-105">Parameters</span></span>  
 `wrappedClasId`  
 <span data-ttu-id="b3451-106">[in] The ID of the class for which the vtable has been created.</span><span class="sxs-lookup"><span data-stu-id="b3451-106">[in] The ID of the class for which the vtable has been created.</span></span>  
  
 `implementedIID`  
 <span data-ttu-id="b3451-107">[in] The ID of the interface implemented by the class.</span><span class="sxs-lookup"><span data-stu-id="b3451-107">[in] The ID of the interface implemented by the class.</span></span> <span data-ttu-id="b3451-108">This value may be NULL if the interface is internal only.</span><span class="sxs-lookup"><span data-stu-id="b3451-108">This value may be NULL if the interface is internal only.</span></span>  
  
 `pVTable`  
 <span data-ttu-id="b3451-109">[in] A pointer to the start of the vtable.</span><span class="sxs-lookup"><span data-stu-id="b3451-109">[in] A pointer to the start of the vtable.</span></span>  
  
 `cSlots`  
 <span data-ttu-id="b3451-110">[in] The number of slots that are in the vtable.</span><span class="sxs-lookup"><span data-stu-id="b3451-110">[in] The number of slots that are in the vtable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b3451-111">주의</span><span class="sxs-lookup"><span data-stu-id="b3451-111">Remarks</span></span>  
 <span data-ttu-id="b3451-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span><span class="sxs-lookup"><span data-stu-id="b3451-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="b3451-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span><span class="sxs-lookup"><span data-stu-id="b3451-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="b3451-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span><span class="sxs-lookup"><span data-stu-id="b3451-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3451-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b3451-115">Requirements</span></span>  
 <span data-ttu-id="b3451-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b3451-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3451-117">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b3451-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b3451-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b3451-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b3451-119">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3451-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3451-120">참조</span><span class="sxs-lookup"><span data-stu-id="b3451-120">See also</span></span>

- [<span data-ttu-id="b3451-121">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b3451-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="b3451-122">COMClassicVTableDestroyed 메서드</span><span class="sxs-lookup"><span data-stu-id="b3451-122">COMClassicVTableDestroyed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtabledestroyed-method.md)
