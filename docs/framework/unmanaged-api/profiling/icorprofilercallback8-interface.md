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
ms.openlocfilehash: 617b27923e96d9abc62ccbf158b076c6e45b20a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175098"
---
# <a name="icorprofilercallback8-interface"></a><span data-ttu-id="30279-102">ICorProfilerCallback8 인터페이스</span><span class="sxs-lookup"><span data-stu-id="30279-102">ICorProfilerCallback8 Interface</span></span>
<span data-ttu-id="30279-103">[.NET 프레임워크 4.7 이후 버전에서 지원]</span><span class="sxs-lookup"><span data-stu-id="30279-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  

 <span data-ttu-id="30279-104">동적 메서드의 JIT 컴파일이 시작되고 완료되었음을 프로파일러에게 알리기 위해 공통 언어 런타임에서 사용하는 콜백 메서드를 제공하는 [ICorProfilerCallback7의](icorprofilercallback7-interface.md) 하위 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="30279-104">A subclass of [ICorProfilerCallback7](icorprofilercallback7-interface.md) that provides callback methods used by the common language runtime to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span>
  
## <a name="methods"></a><span data-ttu-id="30279-105">메서드</span><span class="sxs-lookup"><span data-stu-id="30279-105">Methods</span></span>  
  
|<span data-ttu-id="30279-106">방법</span><span class="sxs-lookup"><span data-stu-id="30279-106">Method</span></span>|<span data-ttu-id="30279-107">Description</span><span class="sxs-lookup"><span data-stu-id="30279-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="30279-108">DynamicMethodJITCompilationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="30279-108">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|<span data-ttu-id="30279-109">동적 메서드의 JIT 컴파일이 시작되었음을 프로파일러에 보오시면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30279-109">Notifies the profiler that JIT compilation of a dynamic method has started.</span></span>|  
|[<span data-ttu-id="30279-110">DynamicMethodJITCompilationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="30279-110">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|<span data-ttu-id="30279-111">동적 메서드의 JIT 컴파일이 완료되었음을 프로파일러에 보오시면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30279-111">Notifies the profiler that JIT compilation of a dynamic method has finished.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="30279-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="30279-112">Requirements</span></span>  
 <span data-ttu-id="30279-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30279-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30279-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="30279-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="30279-115">**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="30279-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="30279-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="30279-116">See also</span></span>

- [<span data-ttu-id="30279-117">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="30279-117">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="30279-118">ICorProfilerCallback9 인터페이스</span><span class="sxs-lookup"><span data-stu-id="30279-118">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
