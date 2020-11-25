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
ms.openlocfilehash: 22a133d02bb69026190428905379323362943d40
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732387"
---
# <a name="icorprofilercallback8-interface"></a><span data-ttu-id="88d6b-102">ICorProfilerCallback8 인터페이스</span><span class="sxs-lookup"><span data-stu-id="88d6b-102">ICorProfilerCallback8 Interface</span></span>

<span data-ttu-id="88d6b-103">[.NET Framework 4.7 이상 버전에서 지원 됨]</span><span class="sxs-lookup"><span data-stu-id="88d6b-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  

 <span data-ttu-id="88d6b-104">공용 언어 런타임에서 동적 메서드의 JIT 컴파일이 시작 및 완료 되었음을 프로파일러에 알리기 위해 사용 하는 콜백 메서드를 제공 하는 [ICorProfilerCallback7](icorprofilercallback7-interface.md) 의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="88d6b-104">A subclass of [ICorProfilerCallback7](icorprofilercallback7-interface.md) that provides callback methods used by the common language runtime to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span>
  
## <a name="methods"></a><span data-ttu-id="88d6b-105">메서드</span><span class="sxs-lookup"><span data-stu-id="88d6b-105">Methods</span></span>  
  
|<span data-ttu-id="88d6b-106">메서드</span><span class="sxs-lookup"><span data-stu-id="88d6b-106">Method</span></span>|<span data-ttu-id="88d6b-107">설명</span><span class="sxs-lookup"><span data-stu-id="88d6b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="88d6b-108">DynamicMethodJITCompilationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="88d6b-108">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|<span data-ttu-id="88d6b-109">동적 메서드의 JIT 컴파일이 시작 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="88d6b-109">Notifies the profiler that JIT compilation of a dynamic method has started.</span></span>|  
|[<span data-ttu-id="88d6b-110">DynamicMethodJITCompilationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="88d6b-110">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|<span data-ttu-id="88d6b-111">동적 메서드의 JIT 컴파일이 완료 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="88d6b-111">Notifies the profiler that JIT compilation of a dynamic method has finished.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="88d6b-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="88d6b-112">Requirements</span></span>  

 <span data-ttu-id="88d6b-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="88d6b-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88d6b-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="88d6b-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="88d6b-115">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="88d6b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="88d6b-116">참조</span><span class="sxs-lookup"><span data-stu-id="88d6b-116">See also</span></span>

- [<span data-ttu-id="88d6b-117">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="88d6b-117">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="88d6b-118">ICorProfilerCallback9 인터페이스</span><span class="sxs-lookup"><span data-stu-id="88d6b-118">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
