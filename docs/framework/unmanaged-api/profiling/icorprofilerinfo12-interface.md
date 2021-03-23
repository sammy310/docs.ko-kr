---
description: '자세히 알아보기: ICorProfilerInfo12 인터페이스'
title: ICorProfilerInfo12 인터페이스
ms.date: 03/19/2021
api_name:
- ICorProfilerInfo12
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: a8b91eba686478c3e825ae15d6ae95bd0ffad944
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805729"
---
# <a name="icorprofilerinfo12-interface"></a><span data-ttu-id="f88a8-103">ICorProfilerInfo12 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f88a8-103">ICorProfilerInfo12 Interface</span></span>

 <span data-ttu-id="f88a8-104">EventPipe 세션, 이벤트 및 공급자를 만드는 메서드를 제공 하는 [ICorProfilerInfo11](icorprofilerinfo11-interface.md) 의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="f88a8-104">A subclass of [ICorProfilerInfo11](icorprofilerinfo11-interface.md) that provides methods to create EventPipe sessions, events, and providers.</span></span>
  
## <a name="methods"></a><span data-ttu-id="f88a8-105">메서드</span><span class="sxs-lookup"><span data-stu-id="f88a8-105">Methods</span></span>  
  
|<span data-ttu-id="f88a8-106">메서드</span><span class="sxs-lookup"><span data-stu-id="f88a8-106">Method</span></span>|<span data-ttu-id="f88a8-107">설명</span><span class="sxs-lookup"><span data-stu-id="f88a8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f88a8-108">EventPipeStartSession 메서드</span><span class="sxs-lookup"><span data-stu-id="f88a8-108">EventPipeStartSession Method</span></span>](icorprofilerinfo12-eventpipestartsession-method.md)|<span data-ttu-id="f88a8-109">프로파일러 EventPipe 세션을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="f88a8-109">Starts a profiler EventPipe session.</span></span>|
|[<span data-ttu-id="f88a8-110">EventPipeAddProviderToSession 메서드</span><span class="sxs-lookup"><span data-stu-id="f88a8-110">EventPipeAddProviderToSession Method</span></span>](icorprofilerinfo12-eventpipeaddprovidertosession-method.md)|<span data-ttu-id="f88a8-111">기존 EventPipe 세션에 공급자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="f88a8-111">Adds a provider to an existing EventPipe session.</span></span>|
|[<span data-ttu-id="f88a8-112">EventPipeStopSession 메서드</span><span class="sxs-lookup"><span data-stu-id="f88a8-112">EventPipeStopSession Method</span></span>](icorprofilerinfo12-eventpipestopsession-method.md)|<span data-ttu-id="f88a8-113">EventPipe 세션을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="f88a8-113">Stops an EventPipe session.</span></span>|
|[<span data-ttu-id="f88a8-114">EventPipeCreateProvider 메서드</span><span class="sxs-lookup"><span data-stu-id="f88a8-114">EventPipeCreateProvider Method</span></span>](icorprofilerinfo12-eventpipecreateprovider-method.md)|<span data-ttu-id="f88a8-115">EventPipe 공급자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f88a8-115">Creates an EventPipe provider.</span></span>|  
|[<span data-ttu-id="f88a8-116">EventPipeGetProviderInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="f88a8-116">EventPipeGetProviderInfo Method</span></span>](icorprofilerinfo12-eventpipegetproviderinfo-method.md)|<span data-ttu-id="f88a8-117">ID에서 EventPipe 공급자의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f88a8-117">Gets the name of an EventPipe provider from its ID.</span></span>|
|[<span data-ttu-id="f88a8-118">EventPipeDefineEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="f88a8-118">EventPipeDefineEvent Method</span></span>](icorprofilerinfo12-eventpipedefineevent-method.md)|<span data-ttu-id="f88a8-119">기존 EventPipe 공급자에서 이벤트를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="f88a8-119">Defines an event on an existing EventPipe provider.</span></span>|  
|[<span data-ttu-id="f88a8-120">EventPipeWriteEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="f88a8-120">EventPipeWriteEvent Method</span></span>](icorprofilerinfo12-eventpipewriteevent-method.md)|<span data-ttu-id="f88a8-121">EventPipe 이벤트를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="f88a8-121">Writes an EventPipe event.</span></span>|
  
## <a name="requirements"></a><span data-ttu-id="f88a8-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f88a8-122">Requirements</span></span>  

<span data-ttu-id="f88a8-123">**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f88a8-123">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>  
<span data-ttu-id="f88a8-124">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f88a8-124">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="f88a8-125">**.Net 버전:**[!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f88a8-125">**.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="f88a8-126">참조</span><span class="sxs-lookup"><span data-stu-id="f88a8-126">See also</span></span>

- [<span data-ttu-id="f88a8-127">EventPipe 개요</span><span class="sxs-lookup"><span data-stu-id="f88a8-127">EventPipe Overview</span></span>](../../../core/diagnostics/eventpipe.md)
- [<span data-ttu-id="f88a8-128">잘 알려진 EventProviders</span><span class="sxs-lookup"><span data-stu-id="f88a8-128">Well Known EventProviders</span></span>](../../../core/diagnostics/well-known-event-providers.md)
- [<span data-ttu-id="f88a8-129">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f88a8-129">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="f88a8-130">ICorProfilerCallback10 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f88a8-130">ICorProfilerCallback10 Interface</span></span>](icorprofilercallback10-interface.md)
