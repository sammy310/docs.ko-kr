---
description: '자세히 알아보기: ICorProfilerCallback3 인터페이스'
title: ICorProfilerCallback3 인터페이스
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3
helpviewer_keywords:
- ICorProfilerCallback3 interface [.NET Framework profiling]
ms.assetid: be83af41-3dec-4c77-8529-9dd6b8042af6
topic_type:
- apiref
ms.openlocfilehash: 70fba8768fef5da411b566d918308989a3f6e863
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99788802"
---
# <a name="icorprofilercallback3-interface"></a><span data-ttu-id="1fdca-103">ICorProfilerCallback3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1fdca-103">ICorProfilerCallback3 Interface</span></span>

<span data-ttu-id="1fdca-104">CLR (공용 언어 런타임)에서 연결 및 분리 상태 정보를 프로파일러에 전달 하는 데 사용 하는 콜백 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1fdca-104">Provides callback methods that the common language runtime (CLR) uses to communicate attach and detach state information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1fdca-105">메서드</span><span class="sxs-lookup"><span data-stu-id="1fdca-105">Methods</span></span>  
  
|<span data-ttu-id="1fdca-106">메서드</span><span class="sxs-lookup"><span data-stu-id="1fdca-106">Method</span></span>|<span data-ttu-id="1fdca-107">설명</span><span class="sxs-lookup"><span data-stu-id="1fdca-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1fdca-108">InitializeForAttach 메서드</span><span class="sxs-lookup"><span data-stu-id="1fdca-108">InitializeForAttach Method</span></span>](icorprofilercallback3-initializeforattach-method.md)|<span data-ttu-id="1fdca-109">프로파일러가 연결 작업 후 상태를 초기화할 수 있도록 하기 위해 CLR에서 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1fdca-109">Called by the CLR to give the profiler an opportunity to initialize its state after an attach operation.</span></span>|  
|[<span data-ttu-id="1fdca-110">ProfilerAttachComplete 메서드</span><span class="sxs-lookup"><span data-stu-id="1fdca-110">ProfilerAttachComplete Method</span></span>](icorprofilercallback3-profilerattachcomplete-method.md)|<span data-ttu-id="1fdca-111">프로파일러가 이제 catch 메서드를 호출할 수 있음을 나타내기 위해 CLR에서 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1fdca-111">Called by the CLR to indicate that the profiler can now call the catch-up methods.</span></span>|  
|[<span data-ttu-id="1fdca-112">ProfilerDetachSucceeded 메서드</span><span class="sxs-lookup"><span data-stu-id="1fdca-112">ProfilerDetachSucceeded Method</span></span>](icorprofilercallback3-profilerdetachsucceeded-method.md)|<span data-ttu-id="1fdca-113">CLR(공용 언어 런타임)이 프로파일러 DLL을 언로드한다고 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="1fdca-113">Notifies the profiler that the common language runtime (CLR) is about to unload the profiler DLL.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1fdca-114">설명</span><span class="sxs-lookup"><span data-stu-id="1fdca-114">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fdca-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1fdca-115">Requirements</span></span>  

 <span data-ttu-id="1fdca-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1fdca-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1fdca-117">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1fdca-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1fdca-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1fdca-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1fdca-119">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fdca-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fdca-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1fdca-120">See also</span></span>

- [<span data-ttu-id="1fdca-121">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1fdca-121">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="1fdca-122">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1fdca-122">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="1fdca-123">ICorProfilerCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1fdca-123">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
- [<span data-ttu-id="1fdca-124">ICorProfilerCallback4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1fdca-124">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
