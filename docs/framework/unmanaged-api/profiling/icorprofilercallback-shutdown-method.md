---
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
ms.openlocfilehash: 490f9dd5446a51bd07881cdb9825d737e380a63e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865859"
---
# <a name="icorprofilercallbackshutdown-method"></a><span data-ttu-id="e46c3-102">ICorProfilerCallback::Shutdown 메서드</span><span class="sxs-lookup"><span data-stu-id="e46c3-102">ICorProfilerCallback::Shutdown Method</span></span>
<span data-ttu-id="e46c3-103">응용 프로그램이 종료 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="e46c3-103">Notifies the profiler that the application is shutting down.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e46c3-104">구문</span><span class="sxs-lookup"><span data-stu-id="e46c3-104">Syntax</span></span>  
  
```cpp  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a><span data-ttu-id="e46c3-105">주의</span><span class="sxs-lookup"><span data-stu-id="e46c3-105">Remarks</span></span>  
 <span data-ttu-id="e46c3-106">`Shutdown` 메서드를 호출한 후에는 프로파일러 코드가 [ICorProfilerInfo](icorprofilerinfo-interface.md) 인터페이스의 메서드를 안전 하 게 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e46c3-106">The profiler code cannot safely call methods of the [ICorProfilerInfo](icorprofilerinfo-interface.md) interface after the `Shutdown` method is called.</span></span> <span data-ttu-id="e46c3-107">`ICorProfilerInfo` 메서드를 호출 하면 `Shutdown` 메서드가 반환 된 후에 정의 되지 않은 동작이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="e46c3-107">Any calls to `ICorProfilerInfo` methods result in undefined behavior after the `Shutdown` method returns.</span></span> <span data-ttu-id="e46c3-108">종료 후에는 변경할 수 없는 특정 이벤트가 계속 발생할 수 있습니다. 이 문제가 발생 하면 프로파일러가 즉시 반환 되도록 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e46c3-108">Certain immutable events may still occur after shutdown; the profiler should take care to return immediately when this occurs.</span></span>  
  
 <span data-ttu-id="e46c3-109">`Shutdown` 메서드는 프로 파일링 되는 관리 되는 응용 프로그램이 관리 코드 (즉, 프로세스 스택의 초기 프레임)로 시작 된 경우에만 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e46c3-109">The `Shutdown` method will be called only if the managed application that is being profiled started as managed code (that is, the initial frame on the process stack is managed).</span></span> <span data-ttu-id="e46c3-110">응용 프로그램이 비관리 코드로 시작 되었지만 나중에 관리 코드로 점프 하 여 CLR (공용 언어 런타임)의 인스턴스를 만든 경우 `Shutdown`가 호출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e46c3-110">If the application started as unmanaged code but later jumped into managed code, thereby creating an instance of the common language runtime (CLR), then `Shutdown` will not be called.</span></span> <span data-ttu-id="e46c3-111">이러한 경우 프로파일러는 DLL_PROCESS_DETACH 값을 사용 하 여 리소스를 해제 하 고 디스크에 추적을 플러시하는 등의 데이터의 정리 처리를 수행 하는 `DllMain` 루틴을 라이브러리에 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e46c3-111">For these cases, the profiler should include in its library a `DllMain` routine that uses the DLL_PROCESS_DETACH value to free any resources and perform clean-up processing of its data, such as flushing traces to disk and so on.</span></span>  
  
 <span data-ttu-id="e46c3-112">일반적으로 프로파일러는 예기치 않은 종료로 대처 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e46c3-112">In general, the profiler must cope with unexpected shutdowns.</span></span> <span data-ttu-id="e46c3-113">예를 들어 Win32's `TerminateProcess` 메서드 (Winbase. h에 선언 됨)에 의해 프로세스가 중단 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e46c3-113">For example, a process might be halted by Win32's `TerminateProcess` method (declared in Winbase.h).</span></span> <span data-ttu-id="e46c3-114">다른 경우에는 CLR에서 특정 관리 되는 스레드 (백그라운드 스레드)에 대 한 순차적 소멸 메시지를 제공 하지 않고 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="e46c3-114">In other cases, the CLR will halt certain managed threads (background threads) without delivering orderly destruction messages for them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e46c3-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e46c3-115">Requirements</span></span>  
 <span data-ttu-id="e46c3-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e46c3-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e46c3-117">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e46c3-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e46c3-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e46c3-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e46c3-119">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e46c3-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e46c3-120">참조</span><span class="sxs-lookup"><span data-stu-id="e46c3-120">See also</span></span>

- [<span data-ttu-id="e46c3-121">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e46c3-121">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="e46c3-122">Initialize 메서드</span><span class="sxs-lookup"><span data-stu-id="e46c3-122">Initialize Method</span></span>](icorprofilercallback-initialize-method.md)
