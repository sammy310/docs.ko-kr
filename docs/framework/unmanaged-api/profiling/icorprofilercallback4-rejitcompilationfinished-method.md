---
description: '자세히 알아보기: ICorProfilerCallback4:: ReJITCompilationFinished 메서드'
title: ICorProfilerCallback4::ReJITCompilationFinished 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITCompilationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITCompilationFinished
helpviewer_keywords:
- ICorProfilerCallback4::ReJITCompilationFinished method [.NET Framework profiling]
- ReJITCompilationFinished method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 3b5cff02-2005-44eb-a2bc-50214c4b0e1d
topic_type:
- apiref
ms.openlocfilehash: 2d7270b5a8cf31fd81505c148429da5f7025319a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99788724"
---
# <a name="icorprofilercallback4rejitcompilationfinished-method"></a><span data-ttu-id="33a23-103">ICorProfilerCallback4::ReJITCompilationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="33a23-103">ICorProfilerCallback4::ReJITCompilationFinished Method</span></span>

<span data-ttu-id="33a23-104">JIT (just-in-time) 컴파일러가 함수를 다시 컴파일 했음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="33a23-104">Notifies the profiler that the just-in-time (JIT) compiler has finished recompiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33a23-105">구문</span><span class="sxs-lookup"><span data-stu-id="33a23-105">Syntax</span></span>  
  
```cpp  
HRESULT ReJITCompilationFinished(  
    [in] FunctionID functionId,    [in] ReJITID rejitId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33a23-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="33a23-106">Parameters</span></span>  

 `functionId`  
 <span data-ttu-id="33a23-107">진행 다시 컴파일된 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="33a23-107">[in] The ID of the function that was recompiled.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="33a23-108">[in] JIT 다시 컴파일된 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="33a23-108">[in] The identity of the JIT-recompiled function.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="33a23-109">진행 JIT 다시 컴파일 성공 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="33a23-109">[in] A value that indicates whether the JIT recompilation was successful.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="33a23-110">[in] `true` 차단으로 인해 런타임에서 호출 스레드가이 콜백에서 반환 될 때까지 대기 하 게 될 수 있음을 나타내려면이 고, `false` 를 지정 하면 차단이 런타임 작업에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="33a23-110">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  
  
 <span data-ttu-id="33a23-111">값은 `true` 런타임에 영향을 주지 않지만 프로 파일링 결과에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33a23-111">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33a23-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="33a23-112">Requirements</span></span>  

 <span data-ttu-id="33a23-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="33a23-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33a23-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="33a23-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="33a23-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33a23-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33a23-116">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33a23-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33a23-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="33a23-117">See also</span></span>

- [<span data-ttu-id="33a23-118">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="33a23-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="33a23-119">ICorProfilerCallback4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="33a23-119">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
- [<span data-ttu-id="33a23-120">JITCompilationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="33a23-120">JITCompilationStarted Method</span></span>](icorprofilercallback-jitcompilationstarted-method.md)
- [<span data-ttu-id="33a23-121">ReJITCompilationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="33a23-121">ReJITCompilationStarted Method</span></span>](icorprofilercallback4-rejitcompilationstarted-method.md)
