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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9d63dd911a5f674a3ce0b02ec78de443c7aebf84
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747163"
---
# <a name="icorprofilercallbackshutdown-method"></a><span data-ttu-id="a71f4-102">ICorProfilerCallback::Shutdown 메서드</span><span class="sxs-lookup"><span data-stu-id="a71f4-102">ICorProfilerCallback::Shutdown Method</span></span>
<span data-ttu-id="a71f4-103">응용 프로그램이 종료 되는 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="a71f4-103">Notifies the profiler that the application is shutting down.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a71f4-104">구문</span><span class="sxs-lookup"><span data-stu-id="a71f4-104">Syntax</span></span>  
  
```cpp  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a><span data-ttu-id="a71f4-105">설명</span><span class="sxs-lookup"><span data-stu-id="a71f4-105">Remarks</span></span>  
 <span data-ttu-id="a71f4-106">프로파일러 코드는의 메서드를 안전 하 게 호출할 수 없습니다는 [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) 후 인터페이스를 `Shutdown` 메서드가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a71f4-106">The profiler code cannot safely call methods of the [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) interface after the `Shutdown` method is called.</span></span> <span data-ttu-id="a71f4-107">에 대 한 모든 호출 `ICorProfilerInfo` 메서드 후 정의 되지 않은 동작이 발생할는 `Shutdown` 메서드 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a71f4-107">Any calls to `ICorProfilerInfo` methods result in undefined behavior after the `Shutdown` method returns.</span></span> <span data-ttu-id="a71f4-108">종료 후 변경할 수 없는 특정 이벤트가 발생할 수 있습니다. 이런 경우 즉시 반환할 프로파일러 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a71f4-108">Certain immutable events may still occur after shutdown; the profiler should take care to return immediately when this occurs.</span></span>  
  
 <span data-ttu-id="a71f4-109">`Shutdown` 프로 파일링 되는 관리 되는 응용 프로그램 관리 코드로 시작 하는 경우에 메서드가 호출 됩니다 (즉, 프로세스 스택의 초기 프레임이 관리 됩니다).</span><span class="sxs-lookup"><span data-stu-id="a71f4-109">The `Shutdown` method will be called only if the managed application that is being profiled started as managed code (that is, the initial frame on the process stack is managed).</span></span> <span data-ttu-id="a71f4-110">응용 프로그램 관리 되지 않는 코드로 시작 하지만 나중에 관리 되는 코드로 이동 하 여 인스턴스를 만들 공용 언어 런타임 (CLR)의 다음 `Shutdown` 호출 되지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a71f4-110">If the application started as unmanaged code but later jumped into managed code, thereby creating an instance of the common language runtime (CLR), then `Shutdown` will not be called.</span></span> <span data-ttu-id="a71f4-111">이러한 경우 프로파일러 해당 라이브러리를 포함 해야 합니다는 `DllMain` 루틴을 DLL_PROCESS_DETACH를 사용 하는 모든 리소스를 해제 하 고 해당 데이터를 추적 하 고 디스크에 플러시하는 등의 정리 프로세스를 수행할 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a71f4-111">For these cases, the profiler should include in its library a `DllMain` routine that uses the DLL_PROCESS_DETACH value to free any resources and perform clean-up processing of its data, such as flushing traces to disk and so on.</span></span>  
  
 <span data-ttu-id="a71f4-112">일반적으로 프로파일러는 예기치 않은 종료를 사용 하 여 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a71f4-112">In general, the profiler must cope with unexpected shutdowns.</span></span> <span data-ttu-id="a71f4-113">Win32의 의해 프로세스를 중단 예를 들어 `TerminateProcess` 메서드 (Winbase.h에 선언 됨).</span><span class="sxs-lookup"><span data-stu-id="a71f4-113">For example, a process might be halted by Win32's `TerminateProcess` method (declared in Winbase.h).</span></span> <span data-ttu-id="a71f4-114">다른 경우에 CLR에 소멸 순서 대로 메시지를 배달 하지 않고 (백그라운드 스레드)는 특정 관리 되는 스레드를 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a71f4-114">In other cases, the CLR will halt certain managed threads (background threads) without delivering orderly destruction messages for them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a71f4-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a71f4-115">Requirements</span></span>  
 <span data-ttu-id="a71f4-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a71f4-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a71f4-117">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a71f4-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a71f4-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a71f4-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a71f4-119">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a71f4-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a71f4-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="a71f4-120">See also</span></span>

- [<span data-ttu-id="a71f4-121">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a71f4-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="a71f4-122">Initialize 메서드</span><span class="sxs-lookup"><span data-stu-id="a71f4-122">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)
