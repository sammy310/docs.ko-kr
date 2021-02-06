---
description: '자세히 알아보기: ICorProfilerCallback:: Shutdown 메서드'
title: ICorProfilerCallback::Shutdown 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.Shutdown
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::Shutdown
helpviewer_keywords:
- ICorProfilerCallback::Shutdown method [.NET Framework profiling]
- Shutdown method [.NET Framework profiling]
ms.assetid: 1ea194f0-a331-4855-a2ce-37393b8e5f84
topic_type:
- apiref
ms.openlocfilehash: 7afc274579f248ee190e379160f2709b5cb9881a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99657322"
---
# <a name="icorprofilercallbackshutdown-method"></a><span data-ttu-id="d21a1-103">ICorProfilerCallback::Shutdown 메서드</span><span class="sxs-lookup"><span data-stu-id="d21a1-103">ICorProfilerCallback::Shutdown Method</span></span>

<span data-ttu-id="d21a1-104">응용 프로그램이 종료 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="d21a1-104">Notifies the profiler that the application is shutting down.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d21a1-105">구문</span><span class="sxs-lookup"><span data-stu-id="d21a1-105">Syntax</span></span>  
  
```cpp  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a><span data-ttu-id="d21a1-106">설명</span><span class="sxs-lookup"><span data-stu-id="d21a1-106">Remarks</span></span>  

 <span data-ttu-id="d21a1-107">메서드를 호출한 후에는 프로파일러 코드가 [ICorProfilerInfo](icorprofilerinfo-interface.md) 인터페이스의 메서드를 안전 하 게 호출할 수 없습니다 `Shutdown` .</span><span class="sxs-lookup"><span data-stu-id="d21a1-107">The profiler code cannot safely call methods of the [ICorProfilerInfo](icorprofilerinfo-interface.md) interface after the `Shutdown` method is called.</span></span> <span data-ttu-id="d21a1-108">메서드를 호출 `ICorProfilerInfo` 하면 메서드가 반환 된 후에 정의 되지 않은 동작이 발생 `Shutdown` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d21a1-108">Any calls to `ICorProfilerInfo` methods result in undefined behavior after the `Shutdown` method returns.</span></span> <span data-ttu-id="d21a1-109">종료 후에는 변경할 수 없는 특정 이벤트가 계속 발생할 수 있습니다. 이 문제가 발생 하면 프로파일러가 즉시 반환 되도록 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d21a1-109">Certain immutable events may still occur after shutdown; the profiler should take care to return immediately when this occurs.</span></span>  
  
 <span data-ttu-id="d21a1-110">메서드는 프로 파일링 되는 관리 되는 `Shutdown` 응용 프로그램이 관리 코드 (즉, 프로세스 스택의 초기 프레임)로 시작 된 경우에만 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d21a1-110">The `Shutdown` method will be called only if the managed application that is being profiled started as managed code (that is, the initial frame on the process stack is managed).</span></span> <span data-ttu-id="d21a1-111">응용 프로그램이 비관리 코드로 시작 되었지만 나중에 관리 코드로 점프 하 여 CLR (공용 언어 런타임)의 인스턴스를 만든 경우에 `Shutdown` 는가 호출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d21a1-111">If the application started as unmanaged code but later jumped into managed code, thereby creating an instance of the common language runtime (CLR), then `Shutdown` will not be called.</span></span> <span data-ttu-id="d21a1-112">이러한 경우 프로파일러는 DLL_PROCESS_DETACH 값을 사용 하 여 리소스를 `DllMain` 해제 하 고 디스크에 추적을 플러시하는 등의 데이터의 정리 처리를 수행 하는 루틴을 라이브러리에 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d21a1-112">For these cases, the profiler should include in its library a `DllMain` routine that uses the DLL_PROCESS_DETACH value to free any resources and perform clean-up processing of its data, such as flushing traces to disk and so on.</span></span>  
  
 <span data-ttu-id="d21a1-113">일반적으로 프로파일러는 예기치 않은 종료로 대처 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d21a1-113">In general, the profiler must cope with unexpected shutdowns.</span></span> <span data-ttu-id="d21a1-114">예를 들어 Win32's `TerminateProcess` 메서드 (Winbase. h에 선언 됨)에 의해 프로세스가 중단 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d21a1-114">For example, a process might be halted by Win32's `TerminateProcess` method (declared in Winbase.h).</span></span> <span data-ttu-id="d21a1-115">다른 경우에는 CLR에서 특정 관리 되는 스레드 (백그라운드 스레드)에 대 한 순차적 소멸 메시지를 제공 하지 않고 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="d21a1-115">In other cases, the CLR will halt certain managed threads (background threads) without delivering orderly destruction messages for them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d21a1-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d21a1-116">Requirements</span></span>  

 <span data-ttu-id="d21a1-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d21a1-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d21a1-118">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d21a1-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d21a1-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d21a1-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d21a1-120">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d21a1-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d21a1-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d21a1-121">See also</span></span>

- [<span data-ttu-id="d21a1-122">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d21a1-122">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="d21a1-123">Initialize 메서드</span><span class="sxs-lookup"><span data-stu-id="d21a1-123">Initialize Method</span></span>](icorprofilercallback-initialize-method.md)
