---
title: ICorProfilerCallback8 인터페이스
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 4516c8f9673052b521c1f0f594978236fef1e0ec
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136447"
---
# <a name="icorprofilercallback8-interface"></a><span data-ttu-id="5d240-102">ICorProfilerCallback8 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5d240-102">ICorProfilerCallback8 Interface</span></span>
<span data-ttu-id="5d240-103">[.NET Framework 4.7 이상 버전에서 지원 됨]</span><span class="sxs-lookup"><span data-stu-id="5d240-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  

 <span data-ttu-id="5d240-104">공용 언어 런타임에서 동적 메서드의 JIT 컴파일이 시작 및 완료 되었음을 프로파일러에 알리기 위해 사용 하는 콜백 메서드를 제공 하는 [ICorProfilerCallback7](icorprofilercallback7-interface.md) 의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="5d240-104">A subclass of [ICorProfilerCallback7](icorprofilercallback7-interface.md) that provides callback methods used by the common language runtime to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span> 
  
## <a name="methods"></a><span data-ttu-id="5d240-105">메서드</span><span class="sxs-lookup"><span data-stu-id="5d240-105">Methods</span></span>  
  
|<span data-ttu-id="5d240-106">메서드</span><span class="sxs-lookup"><span data-stu-id="5d240-106">Method</span></span>|<span data-ttu-id="5d240-107">설명</span><span class="sxs-lookup"><span data-stu-id="5d240-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5d240-108">DynamicMethodJITCompilationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="5d240-108">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|<span data-ttu-id="5d240-109">동적 메서드의 JIT 컴파일이 시작 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="5d240-109">Notifies the profiler that JIT compilation of a dynamic method has started.</span></span>|  
|[<span data-ttu-id="5d240-110">DynamicMethodJITCompilationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="5d240-110">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|<span data-ttu-id="5d240-111">동적 메서드의 JIT 컴파일이 완료 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="5d240-111">Notifies the profiler that JIT compilation of a dynamic method has finished.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5d240-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5d240-112">Requirements</span></span>  
 <span data-ttu-id="5d240-113">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5d240-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d240-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5d240-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="5d240-115">**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5d240-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="5d240-116">참조</span><span class="sxs-lookup"><span data-stu-id="5d240-116">See also</span></span>

- [<span data-ttu-id="5d240-117">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5d240-117">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="5d240-118">ICorProfilerCallback9 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5d240-118">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
