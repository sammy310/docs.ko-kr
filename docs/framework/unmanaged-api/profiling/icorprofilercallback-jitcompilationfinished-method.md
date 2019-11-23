---
title: ICorProfilerCallback::JITCompilationFinished 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCompilationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCompilationFinished
helpviewer_keywords:
- JITCompilationFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationFinished method [.NET Framework profiling]
ms.assetid: 8dcd7537-d0c6-498c-8a56-2c060310ef65
topic_type:
- apiref
ms.openlocfilehash: 1bbdfa93913b9fdf8aa164c8ca6c35cd33a228df
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449913"
---
# <a name="icorprofilercallbackjitcompilationfinished-method"></a><span data-ttu-id="e96af-102">ICorProfilerCallback::JITCompilationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="e96af-102">ICorProfilerCallback::JITCompilationFinished Method</span></span>
<span data-ttu-id="e96af-103">Notifies the profiler that the just-in-time (JIT) compiler has finished compiling a function.</span><span class="sxs-lookup"><span data-stu-id="e96af-103">Notifies the profiler that the just-in-time (JIT) compiler has finished compiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e96af-104">구문</span><span class="sxs-lookup"><span data-stu-id="e96af-104">Syntax</span></span>  
  
```cpp  
HRESULT JITCompilationFinished(  
    [in] FunctionID functionId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e96af-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e96af-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="e96af-106">[in] The ID of the function that was compiled.</span><span class="sxs-lookup"><span data-stu-id="e96af-106">[in] The ID of the function that was compiled.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="e96af-107">[in] A value indicating whether compilation was successful.</span><span class="sxs-lookup"><span data-stu-id="e96af-107">[in] A value indicating whether compilation was successful.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="e96af-108">[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span><span class="sxs-lookup"><span data-stu-id="e96af-108">[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="e96af-109">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span><span class="sxs-lookup"><span data-stu-id="e96af-109">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="e96af-110">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span><span class="sxs-lookup"><span data-stu-id="e96af-110">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e96af-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e96af-111">Requirements</span></span>  
 <span data-ttu-id="e96af-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e96af-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e96af-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e96af-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e96af-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e96af-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e96af-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e96af-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e96af-116">참조</span><span class="sxs-lookup"><span data-stu-id="e96af-116">See also</span></span>

- [<span data-ttu-id="e96af-117">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e96af-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="e96af-118">JITCompilationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="e96af-118">JITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)
