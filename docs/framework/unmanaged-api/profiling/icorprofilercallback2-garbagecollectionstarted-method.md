---
title: ICorProfilerCallback2::GarbageCollectionStarted 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.GarbageCollectionStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::GarbageCollectionStarted
helpviewer_keywords:
- GarbageCollectionStarted method [.NET Framework profiling]
- ICorProfilerCallback2::GarbageCollectionStarted method [.NET Framework profiling]
ms.assetid: 44eef087-f21f-4fe2-b481-f8a0ee022e7d
topic_type:
- apiref
ms.openlocfilehash: 63a8d212a61bd73f44995f0e057eeff96f9a5554
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731955"
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a><span data-ttu-id="478a3-102">ICorProfilerCallback2::GarbageCollectionStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="478a3-102">ICorProfilerCallback2::GarbageCollectionStarted Method</span></span>

<span data-ttu-id="478a3-103">가비지 수집이 시작 되었음을 코드 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="478a3-103">Notifies the code profiler that garbage collection has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="478a3-104">구문</span><span class="sxs-lookup"><span data-stu-id="478a3-104">Syntax</span></span>  
  
```cpp  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="478a3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="478a3-105">Parameters</span></span>  

 `cGenerations`  
 <span data-ttu-id="478a3-106">진행 배열의 총 항목 수 `generationCollected` 입니다.</span><span class="sxs-lookup"><span data-stu-id="478a3-106">[in] The total number of entries in the `generationCollected` array.</span></span>  
  
 `generationCollected`  
 <span data-ttu-id="478a3-107">진행 `true` 이 가비지 컬렉션에서 배열 인덱스에 해당 하는 생성을 수집 하 고 있으면이 고, 그렇지 않으면 인 부울 값의 배열입니다 `false` .</span><span class="sxs-lookup"><span data-stu-id="478a3-107">[in] An array of Boolean values, which are `true` if the generation that corresponds to the array index is being collected by this garbage collection; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="478a3-108">배열은 생성을 나타내는 [COR_PRF_GC_GENERATION](cor-prf-gc-generation-enumeration.md) 열거형 값으로 인덱싱됩니다.</span><span class="sxs-lookup"><span data-stu-id="478a3-108">The array is indexed by a value of the [COR_PRF_GC_GENERATION](cor-prf-gc-generation-enumeration.md) enumeration, which indicates the generation.</span></span>  
  
 `reason`  
 <span data-ttu-id="478a3-109">진행 가비지 컬렉션이 발생 한 이유를 나타내는 [COR_PRF_GC_REASON](cor-prf-gc-reason-enumeration.md) 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="478a3-109">[in] A value of the [COR_PRF_GC_REASON](cor-prf-gc-reason-enumeration.md) enumeration that indicates the reason the garbage collection was induced.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="478a3-110">설명</span><span class="sxs-lookup"><span data-stu-id="478a3-110">Remarks</span></span>  

 <span data-ttu-id="478a3-111">이 가비지 컬렉션과 관련 된 모든 콜백은 콜백과 `GarbageCollectionStarted` 해당 [ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) callback 사이에서 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="478a3-111">All callbacks that pertain to this garbage collection will occur between the `GarbageCollectionStarted` callback and the corresponding [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) callback.</span></span> <span data-ttu-id="478a3-112">이러한 콜백은 동일한 스레드에서 발생 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="478a3-112">These callbacks need not occur on the same thread.</span></span>  
  
 <span data-ttu-id="478a3-113">프로파일러에서는 콜백 중에 원래 위치에 있는 개체를 검사 하는 것이 안전 `GarbageCollectionStarted` 합니다.</span><span class="sxs-lookup"><span data-stu-id="478a3-113">It is safe for the profiler to inspect objects in their original locations during the `GarbageCollectionStarted` callback.</span></span> <span data-ttu-id="478a3-114">에서 반환 된 후 가비지 수집기가 개체 이동을 시작 합니다 `GarbageCollectionStarted` .</span><span class="sxs-lookup"><span data-stu-id="478a3-114">The garbage collector will begin moving objects after the return from `GarbageCollectionStarted`.</span></span> <span data-ttu-id="478a3-115">프로파일러가이 콜백에서 반환한 후 프로파일러는 콜백을 받을 때까지 모든 개체 Id가 유효 하지 않은 것으로 간주 해야 합니다 `ICorProfilerCallback2::GarbageCollectionFinished` .</span><span class="sxs-lookup"><span data-stu-id="478a3-115">After the profiler has returned from this callback, the profiler should consider all object IDs to be invalid until it receives a `ICorProfilerCallback2::GarbageCollectionFinished` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="478a3-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="478a3-116">Requirements</span></span>  

 <span data-ttu-id="478a3-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="478a3-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="478a3-118">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="478a3-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="478a3-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="478a3-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="478a3-120">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="478a3-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="478a3-121">참조</span><span class="sxs-lookup"><span data-stu-id="478a3-121">See also</span></span>

- [<span data-ttu-id="478a3-122">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="478a3-122">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="478a3-123">ICorProfilerCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="478a3-123">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
