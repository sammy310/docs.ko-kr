---
title: ICorProfilerCallback3 인터페이스
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3
helpviewer_keywords:
- ICorProfilerCallback3 interface [.NET Framework profiling]
ms.assetid: be83af41-3dec-4c77-8529-9dd6b8042af6
topic_type:
- apiref
ms.openlocfilehash: fd482bfe8e95a53cafd1530c88f09df146a1b150
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729436"
---
# <a name="icorprofilercallback3-interface"></a><span data-ttu-id="f783c-102">ICorProfilerCallback3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f783c-102">ICorProfilerCallback3 Interface</span></span>

<span data-ttu-id="f783c-103">CLR (공용 언어 런타임)에서 연결 및 분리 상태 정보를 프로파일러에 전달 하는 데 사용 하는 콜백 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f783c-103">Provides callback methods that the common language runtime (CLR) uses to communicate attach and detach state information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f783c-104">메서드</span><span class="sxs-lookup"><span data-stu-id="f783c-104">Methods</span></span>  
  
|<span data-ttu-id="f783c-105">메서드</span><span class="sxs-lookup"><span data-stu-id="f783c-105">Method</span></span>|<span data-ttu-id="f783c-106">설명</span><span class="sxs-lookup"><span data-stu-id="f783c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f783c-107">InitializeForAttach 메서드</span><span class="sxs-lookup"><span data-stu-id="f783c-107">InitializeForAttach Method</span></span>](icorprofilercallback3-initializeforattach-method.md)|<span data-ttu-id="f783c-108">프로파일러가 연결 작업 후 상태를 초기화할 수 있도록 하기 위해 CLR에서 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f783c-108">Called by the CLR to give the profiler an opportunity to initialize its state after an attach operation.</span></span>|  
|[<span data-ttu-id="f783c-109">ProfilerAttachComplete 메서드</span><span class="sxs-lookup"><span data-stu-id="f783c-109">ProfilerAttachComplete Method</span></span>](icorprofilercallback3-profilerattachcomplete-method.md)|<span data-ttu-id="f783c-110">프로파일러가 이제 catch 메서드를 호출할 수 있음을 나타내기 위해 CLR에서 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f783c-110">Called by the CLR to indicate that the profiler can now call the catch-up methods.</span></span>|  
|[<span data-ttu-id="f783c-111">ProfilerDetachSucceeded 메서드</span><span class="sxs-lookup"><span data-stu-id="f783c-111">ProfilerDetachSucceeded Method</span></span>](icorprofilercallback3-profilerdetachsucceeded-method.md)|<span data-ttu-id="f783c-112">CLR(공용 언어 런타임)이 프로파일러 DLL을 언로드한다고 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="f783c-112">Notifies the profiler that the common language runtime (CLR) is about to unload the profiler DLL.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f783c-113">설명</span><span class="sxs-lookup"><span data-stu-id="f783c-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f783c-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f783c-114">Requirements</span></span>  

 <span data-ttu-id="f783c-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f783c-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f783c-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f783c-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f783c-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f783c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f783c-118">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f783c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f783c-119">참조</span><span class="sxs-lookup"><span data-stu-id="f783c-119">See also</span></span>

- [<span data-ttu-id="f783c-120">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f783c-120">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="f783c-121">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f783c-121">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="f783c-122">ICorProfilerCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f783c-122">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
- [<span data-ttu-id="f783c-123">ICorProfilerCallback4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f783c-123">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
