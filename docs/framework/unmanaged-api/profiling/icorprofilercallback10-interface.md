---
description: '자세히 알아보기: ICorProfilerCallback10 인터페이스'
title: ICorProfilerCallback10 인터페이스
ms.date: 03/19/2021
api_name:
- ICorProfilerCallback10
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: d9091dc81307e2dcb83e74154a8217dffaa1e7a2
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805651"
---
# <a name="icorprofilercallback10-interface"></a><span data-ttu-id="1ff6d-103">ICorProfilerCallback10 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1ff6d-103">ICorProfilerCallback10 Interface</span></span>

 <span data-ttu-id="1ff6d-104">EventPipe 이벤트가 프로파일러의 현재 활성 세션에 전달 되었음을 프로파일러에 알리는 콜백 메서드를 제공 하는 [ICorProfilerCallback9](icorprofilercallback9-interface.md) 의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="1ff6d-104">A subclass of [ICorProfilerCallback9](icorprofilercallback9-interface.md) that provides callback methods to notify the profiler that EventPipe events have been delivered to the profiler's currently active session.</span></span>
  
## <a name="methods"></a><span data-ttu-id="1ff6d-105">메서드</span><span class="sxs-lookup"><span data-stu-id="1ff6d-105">Methods</span></span>  
  
|<span data-ttu-id="1ff6d-106">메서드</span><span class="sxs-lookup"><span data-stu-id="1ff6d-106">Method</span></span>|<span data-ttu-id="1ff6d-107">설명</span><span class="sxs-lookup"><span data-stu-id="1ff6d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1ff6d-108">EventPipeEventDelivered 메서드</span><span class="sxs-lookup"><span data-stu-id="1ff6d-108">EventPipeEventDelivered Method</span></span>](icorprofilercallback10-eventpipeeventdelivered-method.md)|<span data-ttu-id="1ff6d-109">프로파일러에서 연 세션에 EventPipe 이벤트가 전달 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="1ff6d-109">Notifies the profiler that an EventPipe event has been delivered to the session that the profiler has open.</span></span>|
|[<span data-ttu-id="1ff6d-110">EventPipeProviderCreated 메서드</span><span class="sxs-lookup"><span data-stu-id="1ff6d-110">EventPipeProviderCreated Method</span></span>](icorprofilercallback10-eventpipeprovidercreated-method.md)|<span data-ttu-id="1ff6d-111">프로파일러가 EventPipe 공급자를 만들었음을 알리기 때문에 프로파일러가 해당 공급자의 세션을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ff6d-111">Notifies the profiler that an EventPipe provider has been created, allowing the profiler to add that provider the their session.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1ff6d-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1ff6d-112">Requirements</span></span>  

<span data-ttu-id="1ff6d-113">**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1ff6d-113">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>  
<span data-ttu-id="1ff6d-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1ff6d-114">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="1ff6d-115">**.Net 버전:**[!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ff6d-115">**.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="1ff6d-116">참조</span><span class="sxs-lookup"><span data-stu-id="1ff6d-116">See also</span></span>

- [<span data-ttu-id="1ff6d-117">EventPipe 개요</span><span class="sxs-lookup"><span data-stu-id="1ff6d-117">EventPipe Overview</span></span>](../../../core/diagnostics/eventpipe.md)
- [<span data-ttu-id="1ff6d-118">잘 알려진 EventProviders</span><span class="sxs-lookup"><span data-stu-id="1ff6d-118">Well Known EventProviders</span></span>](../../../core/diagnostics/well-known-event-providers.md)
- [<span data-ttu-id="1ff6d-119">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1ff6d-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="1ff6d-120">ICorProfilerInfo12 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1ff6d-120">ICorProfilerInfo12 Interface</span></span>](ICorProfilerInfo12-interface.md)
- [<span data-ttu-id="1ff6d-121">ICorProfilerInfo12 EventPipeStartSession 메서드</span><span class="sxs-lookup"><span data-stu-id="1ff6d-121">ICorProfilerInfo12.EventPipeStartSession method</span></span>](ICorProfilerInfo12-eventpipestartsession-method.md)
- [<span data-ttu-id="1ff6d-122">ICorProfilerInfo12 EventPipeStopSession 메서드</span><span class="sxs-lookup"><span data-stu-id="1ff6d-122">ICorProfilerInfo12.EventPipeStopSession method</span></span>](ICorProfilerInfo12-eventpipestopsession-method.md)
