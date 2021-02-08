---
description: '자세히 알아보기: ICorProfilerCallback8 인터페이스'
title: ICorProfilerCallback8 인터페이스
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 8dd9b8eea82f38b7598d578bd718743af826070d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781677"
---
# <a name="icorprofilercallback8-interface"></a><span data-ttu-id="d8d07-103">ICorProfilerCallback8 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d8d07-103">ICorProfilerCallback8 Interface</span></span>

<span data-ttu-id="d8d07-104">[.NET Framework 4.7 이상 버전에서 지원 됨]</span><span class="sxs-lookup"><span data-stu-id="d8d07-104">[Supported in the .NET Framework 4.7 and later versions]</span></span>  

 <span data-ttu-id="d8d07-105">공용 언어 런타임에서 동적 메서드의 JIT 컴파일이 시작 및 완료 되었음을 프로파일러에 알리기 위해 사용 하는 콜백 메서드를 제공 하는 [ICorProfilerCallback7](icorprofilercallback7-interface.md) 의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="d8d07-105">A subclass of [ICorProfilerCallback7](icorprofilercallback7-interface.md) that provides callback methods used by the common language runtime to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span>
  
## <a name="methods"></a><span data-ttu-id="d8d07-106">메서드</span><span class="sxs-lookup"><span data-stu-id="d8d07-106">Methods</span></span>  
  
|<span data-ttu-id="d8d07-107">메서드</span><span class="sxs-lookup"><span data-stu-id="d8d07-107">Method</span></span>|<span data-ttu-id="d8d07-108">설명</span><span class="sxs-lookup"><span data-stu-id="d8d07-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d8d07-109">DynamicMethodJITCompilationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="d8d07-109">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|<span data-ttu-id="d8d07-110">동적 메서드의 JIT 컴파일이 시작 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="d8d07-110">Notifies the profiler that JIT compilation of a dynamic method has started.</span></span>|  
|[<span data-ttu-id="d8d07-111">DynamicMethodJITCompilationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="d8d07-111">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|<span data-ttu-id="d8d07-112">동적 메서드의 JIT 컴파일이 완료 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="d8d07-112">Notifies the profiler that JIT compilation of a dynamic method has finished.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d8d07-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d8d07-113">Requirements</span></span>  

 <span data-ttu-id="d8d07-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8d07-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8d07-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d8d07-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="d8d07-116">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d8d07-116">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="d8d07-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d8d07-117">See also</span></span>

- [<span data-ttu-id="d8d07-118">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d8d07-118">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="d8d07-119">ICorProfilerCallback9 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d8d07-119">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
