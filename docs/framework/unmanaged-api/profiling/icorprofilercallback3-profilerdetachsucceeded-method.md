---
description: ICorProfilerCallback3::P rofilerDetachSucceeded 메서드에 대해 자세히 알아보세요.
title: ICorProfilerCallback3::ProfilerDetachSucceeded 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3.ProfilerDetachSucceeded Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3::ProfilerDetachSucceeded
helpviewer_keywords:
- ProfilerDetachSucceeded method [.NET Framework profiling]
- ICorProfilerCallback3::ProfilerDetachSucceeded method [.NET Framework profiling]
ms.assetid: 05164966-16ce-4cc9-a530-43a640c00711
topic_type:
- apiref
ms.openlocfilehash: bc80b5bd5301bb5b0278534cfba6ac23e5968620
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99788776"
---
# <a name="icorprofilercallback3profilerdetachsucceeded-method"></a><span data-ttu-id="01113-103">ICorProfilerCallback3::ProfilerDetachSucceeded 메서드</span><span class="sxs-lookup"><span data-stu-id="01113-103">ICorProfilerCallback3::ProfilerDetachSucceeded Method</span></span>

<span data-ttu-id="01113-104">CLR(공용 언어 런타임)이 프로파일러 DLL을 언로드한다고 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="01113-104">Notifies the profiler that the common language runtime (CLR) is about to unload the profiler DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01113-105">구문</span><span class="sxs-lookup"><span data-stu-id="01113-105">Syntax</span></span>  
  
```cpp  
HRESULT ProfilerDetachSucceeded();  
```  
  
## <a name="return-value"></a><span data-ttu-id="01113-106">Return Value</span><span class="sxs-lookup"><span data-stu-id="01113-106">Return Value</span></span>  

 <span data-ttu-id="01113-107">이 콜백의 반환 값은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="01113-107">The return value from this callback is ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01113-108">설명</span><span class="sxs-lookup"><span data-stu-id="01113-108">Remarks</span></span>  

 <span data-ttu-id="01113-109">`ProfilerDetachSucceeded` 콜백은 모든 스레드가 프로파일러의 코드를 종료한 후에 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="01113-109">The `ProfilerDetachSucceeded` callback is issued after all threads have exited the profiler's code.</span></span> <span data-ttu-id="01113-110">이 메서드가 호출되면 프로파일러는 UI 또는 로깅 구성 요소에 알림과 같은 소멸자에 적합하지 않은 마지막 작업을 모두 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01113-110">When this method is called, the profiler should perform any last-minute tasks that are not appropriate for its destructor, such as notifying its UI or logging component.</span></span> <span data-ttu-id="01113-111">그러나 프로파일러는이 콜백 중 CLR에서 제공 하는 인터페이스 (예: [ICorProfilerInfo](icorprofilerinfo-interface.md) 또는 인터페이스)에서 함수를 호출 하면 안 `IMetaData*` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01113-111">However, the profiler must not call functions on interfaces that are provided by the CLR during this callback (such as the [ICorProfilerInfo](icorprofilerinfo-interface.md) or `IMetaData*` interfaces).</span></span>  
  
 <span data-ttu-id="01113-112">CLR은 Windows 애플리케이션 이벤트 로그에 항목을 만들어 분리 작업에 성공했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="01113-112">The CLR creates an entry in the Windows Application event log to indicate that the detach operation is successful.</span></span>  
  
 <span data-ttu-id="01113-113">프로파일러가 이 콜백에서 반환된 후 CLR은 프로파일러 개체를 해제하고 프로파일러 DLL을 언로드합니다.</span><span class="sxs-lookup"><span data-stu-id="01113-113">After the profiler returns from this callback, the CLR releases the profiler object and unloads the profiler DLL.</span></span> <span data-ttu-id="01113-114">따라서 프로파일러는 이 콜백에서 반환된 후 프로파일러 DLL 내에서 실행되는 작업을 수행하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01113-114">Therefore, the profiler must not perform any actions that would cause execution to occur inside the profiler DLL after it returns from this callback.</span></span> <span data-ttu-id="01113-115">예를 들어 스레드를 만들거나 타이머 콜백을 등록하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01113-115">For example, it must not create threads or register timer callbacks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01113-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="01113-116">Requirements</span></span>  

 <span data-ttu-id="01113-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="01113-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01113-118">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="01113-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="01113-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="01113-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="01113-120">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01113-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01113-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="01113-121">See also</span></span>

- [<span data-ttu-id="01113-122">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="01113-122">Metadata Interfaces</span></span>](../metadata/metadata-interfaces.md)
- [<span data-ttu-id="01113-123">ICorProfilerInfo3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="01113-123">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="01113-124">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="01113-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="01113-125">프로파일링</span><span class="sxs-lookup"><span data-stu-id="01113-125">Profiling</span></span>](index.md)
