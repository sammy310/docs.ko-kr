---
title: ICorProfilerCallback9 인터페이스
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: c383a2e221e61770d3c28a65c561c48f6059b6d6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136573"
---
# <a name="icorprofilercallback9-interface"></a><span data-ttu-id="09107-102">ICorProfilerCallback9 인터페이스</span><span class="sxs-lookup"><span data-stu-id="09107-102">ICorProfilerCallback9 Interface</span></span>
<span data-ttu-id="09107-103">[.NET Framework 4.7.2 이상 버전에서 지원 됨]</span><span class="sxs-lookup"><span data-stu-id="09107-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  

 <span data-ttu-id="09107-104">공용 언어 런타임에서 동적 메서드가 가비지 수집 되 고 이후에 언로드되는 것을 프로파일러에 알리는 데 사용 하는 콜백 메서드를 제공 하는 [ICorProfilerCallback8](icorprofilercallback8-interface.md) 의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="09107-104">A subclass of [ICorProfilerCallback8](icorprofilercallback8-interface.md) that provides a callback method used by the common language runtime to notify the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="09107-105">메서드</span><span class="sxs-lookup"><span data-stu-id="09107-105">Methods</span></span>  
  
|<span data-ttu-id="09107-106">메서드</span><span class="sxs-lookup"><span data-stu-id="09107-106">Method</span></span>|<span data-ttu-id="09107-107">설명</span><span class="sxs-lookup"><span data-stu-id="09107-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="09107-108">DynamicMethodUnloaded 메서드</span><span class="sxs-lookup"><span data-stu-id="09107-108">DynamicMethodUnloaded Method</span></span>](ICorProfilerCallback9-dynamicmethodunloaded-method.md)|<span data-ttu-id="09107-109">동적 메서드가 가비지 수집 되 고 이후에 언로드되는 것을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="09107-109">Notifies the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="09107-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="09107-110">Requirements</span></span>  
 <span data-ttu-id="09107-111">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09107-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09107-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="09107-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="09107-113">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="09107-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="09107-114">참조</span><span class="sxs-lookup"><span data-stu-id="09107-114">See also</span></span>

- [<span data-ttu-id="09107-115">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="09107-115">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="09107-116">ICorProfilerCallback8 인터페이스</span><span class="sxs-lookup"><span data-stu-id="09107-116">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="09107-117">ICorProfilerCallback8 DynamicMethodJITCompilationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="09107-117">ICorProfilerCallback8.DynamicMethodJITCompilationStarted method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="09107-118">ICorProfilerCallback8 DynamicMethodJITCompilationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="09107-118">ICorProfilerCallback8.DynamicMethodJITCompilationFinished method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
