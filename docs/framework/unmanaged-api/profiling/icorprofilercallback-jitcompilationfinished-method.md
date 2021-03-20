---
description: '자세히 알아보기: ICorProfilerCallback:: JITCompilationFinished 메서드'
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
ms.openlocfilehash: 32a47860ae2e973d32ef12b2bd9002bb1de45ee9
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760329"
---
# <a name="icorprofilercallbackjitcompilationfinished-method"></a><span data-ttu-id="a7e44-103">ICorProfilerCallback::JITCompilationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="a7e44-103">ICorProfilerCallback::JITCompilationFinished Method</span></span>

<span data-ttu-id="a7e44-104">JIT (just-in-time) 컴파일러가 함수 컴파일을 완료 했음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="a7e44-104">Notifies the profiler that the just-in-time (JIT) compiler has finished compiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7e44-105">구문</span><span class="sxs-lookup"><span data-stu-id="a7e44-105">Syntax</span></span>  
  
```cpp  
HRESULT JITCompilationFinished(  
    [in] FunctionID functionId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7e44-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a7e44-106">Parameters</span></span>

<span data-ttu-id="a7e44-107">`functionId` 진행 컴파일된 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a7e44-107">`functionId` [in] The ID of the function that was compiled.</span></span>

<span data-ttu-id="a7e44-108">`hrStatus` 진행 컴파일이 성공 했는지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a7e44-108">`hrStatus` [in] A value indicating whether compilation was successful.</span></span>

<span data-ttu-id="a7e44-109">`fIsSafeToBlock` 진행 차단이 런타임 작업에 영향을 주는지 여부를 프로파일러에 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a7e44-109">`fIsSafeToBlock` [in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="a7e44-110">`true`차단 하면 호출 스레드가이 콜백에서 반환 될 때까지 런타임이 대기 하 게 될 수 있으면 값이이 고, 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="a7e44-110">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>

<span data-ttu-id="a7e44-111">값은 `true` 런타임에 영향을 주지 않지만 프로 파일링 결과를 기울일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7e44-111">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>

## <a name="requirements"></a><span data-ttu-id="a7e44-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a7e44-112">Requirements</span></span>  

 <span data-ttu-id="a7e44-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a7e44-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7e44-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a7e44-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a7e44-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7e44-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7e44-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7e44-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7e44-117">참조</span><span class="sxs-lookup"><span data-stu-id="a7e44-117">See also</span></span>

- [<span data-ttu-id="a7e44-118">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a7e44-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="a7e44-119">JITCompilationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="a7e44-119">JITCompilationStarted Method</span></span>](icorprofilercallback-jitcompilationstarted-method.md)
