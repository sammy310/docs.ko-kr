---
description: '자세히 알아보기: ICorProfilerInfo4:: InitializeCurrentThread 메서드'
title: ICorProfilerInfo4::InitializeCurrentThread 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4::InitializeCurrentThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::InitializeCurrentThread
helpviewer_keywords:
- ICorProfilerInfo4::InitializeCurrentThread method [.NET Framework profiling]
- InitializeCurrentThread method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 18a3335c-8c75-476c-b6de-72c0bfedae5d
topic_type:
- apiref
ms.openlocfilehash: a78816c736507a4a59da3ea1c75b078b54c34125
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781406"
---
# <a name="icorprofilerinfo4initializecurrentthread-method"></a><span data-ttu-id="965d2-103">ICorProfilerInfo4::InitializeCurrentThread 메서드</span><span class="sxs-lookup"><span data-stu-id="965d2-103">ICorProfilerInfo4::InitializeCurrentThread Method</span></span>

<span data-ttu-id="965d2-104">교착 상태를 방지할 수 있도록 동일한 스레드에서 후속 프로파일러 API 호출을 앞서 현재 스레드를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="965d2-104">Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="965d2-105">구문</span><span class="sxs-lookup"><span data-stu-id="965d2-105">Syntax</span></span>  
  
```cpp  
HRESULT InitializeCurrentThread ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="965d2-106">설명</span><span class="sxs-lookup"><span data-stu-id="965d2-106">Remarks</span></span>  

 <span data-ttu-id="965d2-107">`InitializeCurrentThread`일시 중단 된 스레드가 있는 동안 프로파일러 API를 호출 하는 모든 스레드에서를 호출 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="965d2-107">We recommend that you call `InitializeCurrentThread` on any thread that will call a profiler API while there are suspended threads.</span></span> <span data-ttu-id="965d2-108">이 메서드는 일반적으로 [ICorProfilerInfo2::D ostacksnapshot](icorprofilerinfo2-dostacksnapshot-method.md) 메서드를 호출 하 여 대상 스레드가 일시 중단 된 동안 스택 워크를 수행 하는 자체 스레드를 만드는 샘플링 프로파일러에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="965d2-108">This method is typically used by sampling profilers that create their own thread to call the [ICorProfilerInfo2::DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) method to perform stack walks while the target thread is suspended.</span></span> <span data-ttu-id="965d2-109">`InitializeCurrentThread`프로파일러가 먼저 샘플링 스레드를 만들 때를 한 번 호출 하 여 프로파일러는 `DoStackSnapshot` 다른 스레드가 일시 중단 되지 않은 경우에 대 한 첫 번째 호출을 수행 하는 동안 CLR에서 수행 하는 지연 스레드 단위 초기화를 수행할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="965d2-109">By calling `InitializeCurrentThread` once when the profiler first creates the sampling thread, profilers can ensure that lazy per-thread initialization that the CLR would otherwise perform during the first call to `DoStackSnapshot` can now occur safely when no other threads are suspended.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="965d2-110">`InitializeCurrentThread` 는 잠금을 수행 하는 작업을 완료 하도록 미리 초기화를 수행 하 고 교착 상태를 발생 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="965d2-110">`InitializeCurrentThread` does the initialization in advance to finish tasks that take locks, and may deadlock.</span></span> <span data-ttu-id="965d2-111">`InitializeCurrentThread`일시 중단 된 스레드가 없는 경우에만를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="965d2-111">Call `InitializeCurrentThread` only when there are no suspended threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="965d2-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="965d2-112">Requirements</span></span>  

 <span data-ttu-id="965d2-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="965d2-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="965d2-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="965d2-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="965d2-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="965d2-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="965d2-116">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="965d2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="965d2-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="965d2-117">See also</span></span>

- [<span data-ttu-id="965d2-118">ICorProfilerInfo4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="965d2-118">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="965d2-119">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="965d2-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="965d2-120">프로파일링</span><span class="sxs-lookup"><span data-stu-id="965d2-120">Profiling</span></span>](index.md)
