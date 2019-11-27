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
# <a name="icorprofilercallbackjitcompilationfinished-method"></a><span data-ttu-id="dcc9e-102">ICorProfilerCallback::JITCompilationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="dcc9e-102">ICorProfilerCallback::JITCompilationFinished Method</span></span>
<span data-ttu-id="dcc9e-103">JIT (just-in-time) 컴파일러가 함수 컴파일을 완료 했음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="dcc9e-103">Notifies the profiler that the just-in-time (JIT) compiler has finished compiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcc9e-104">구문</span><span class="sxs-lookup"><span data-stu-id="dcc9e-104">Syntax</span></span>  
  
```cpp  
HRESULT JITCompilationFinished(  
    [in] FunctionID functionId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dcc9e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dcc9e-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="dcc9e-106">진행 컴파일된 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="dcc9e-106">[in] The ID of the function that was compiled.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="dcc9e-107">진행 컴파일이 성공 했는지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="dcc9e-107">[in] A value indicating whether compilation was successful.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="dcc9e-108">진행 차단이 런타임 작업에 영향을 주는지 여부를 프로파일러에 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="dcc9e-108">[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="dcc9e-109">차단으로 인해 런타임에서 호출 스레드가이 콜백에서 반환 될 때까지 대기 하는 경우 값이 `true` 됩니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc9e-109">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="dcc9e-110">`true` 값은 런타임에 영향을 주지 않지만 프로 파일링 결과를 기울일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc9e-110">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcc9e-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dcc9e-111">Requirements</span></span>  
 <span data-ttu-id="dcc9e-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dcc9e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcc9e-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="dcc9e-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="dcc9e-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dcc9e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dcc9e-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcc9e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcc9e-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dcc9e-116">See also</span></span>

- [<span data-ttu-id="dcc9e-117">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dcc9e-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="dcc9e-118">JITCompilationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="dcc9e-118">JITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)
