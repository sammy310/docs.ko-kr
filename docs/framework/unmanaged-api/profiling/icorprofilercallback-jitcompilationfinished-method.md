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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1abc4dd209581c9f7c8e950ea1addc74c611d248
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59226060"
---
# <a name="icorprofilercallbackjitcompilationfinished-method"></a><span data-ttu-id="fed3b-102">ICorProfilerCallback::JITCompilationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="fed3b-102">ICorProfilerCallback::JITCompilationFinished Method</span></span>
<span data-ttu-id="fed3b-103">Just-in-time (JIT) 컴파일러가 함수 컴파일이 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="fed3b-103">Notifies the profiler that the just-in-time (JIT) compiler has finished compiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fed3b-104">구문</span><span class="sxs-lookup"><span data-stu-id="fed3b-104">Syntax</span></span>  
  
```  
HRESULT JITCompilationFinished(  
    [in] FunctionID functionId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fed3b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fed3b-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="fed3b-106">[in] 컴파일된 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fed3b-106">[in] The ID of the function that was compiled.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="fed3b-107">[in] 컴파일 성공 했는지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fed3b-107">[in] A value indicating whether compilation was successful.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="fed3b-108">[in] 프로파일러 차단 여부를 나타내는 값을 런타임 작업에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fed3b-108">[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="fed3b-109">값이 `true` 런타임에서이 콜백에서; 반환할 호출 스레드에 대 한 대기를 차단 않을 경우이 고, 그렇지 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="fed3b-109">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="fed3b-110">하지만 값 `true` 런타임 나쁜 영향을 주지, 프로 파일링 결과 기울일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fed3b-110">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fed3b-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fed3b-111">Requirements</span></span>  
 <span data-ttu-id="fed3b-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fed3b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fed3b-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fed3b-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fed3b-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fed3b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fed3b-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fed3b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fed3b-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="fed3b-116">See also</span></span>

- [<span data-ttu-id="fed3b-117">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fed3b-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="fed3b-118">JITCompilationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="fed3b-118">JITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)
