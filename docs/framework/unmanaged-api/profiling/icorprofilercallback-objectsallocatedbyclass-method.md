---
title: ICorProfilerCallback::ObjectsAllocatedByClass 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectsAllocatedByClass
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectsAllocatedByClass
helpviewer_keywords:
- ObjectsAllocatedByClass method [.NET Framework profiling]
- ICorProfilerCallback::ObjectsAllocatedByClass method [.NET Framework profiling]
ms.assetid: 91d688f3-a80e-419d-9755-ff94bc04188a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b9f5d2c08abbcab6bc1a6d0569b8e70d7c919def
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59195867"
---
# <a name="icorprofilercallbackobjectsallocatedbyclass-method"></a><span data-ttu-id="19725-102">ICorProfilerCallback::ObjectsAllocatedByClass 메서드</span><span class="sxs-lookup"><span data-stu-id="19725-102">ICorProfilerCallback::ObjectsAllocatedByClass Method</span></span>
<span data-ttu-id="19725-103">가장 최근의 가비지 수집 이후 생성 된 각 지정 된 클래스의 인스턴스 수에 대 한 프로파일러를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="19725-103">Notifies the profiler about the number of instances of each specified class that have been created since the most recent garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19725-104">구문</span><span class="sxs-lookup"><span data-stu-id="19725-104">Syntax</span></span>  
  
```  
HRESULT ObjectsAllocatedByClass(  
    [in] ULONG   cClassCount,  
    [in, size_is(cClassCount)] ClassID classIds[] ,  
    [in, size_is(cClassCount)] ULONG   cObjects[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="19725-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="19725-105">Parameters</span></span>  
 `cClassCount`  
 <span data-ttu-id="19725-106">[in] 크기를 `classIds` 고 `cObjects` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="19725-106">[in] The size of the `classIds` and `cObjects` arrays.</span></span>  
  
 `classIds`  
 <span data-ttu-id="19725-107">[in] 배열 클래스 Id 각 ID 하나 이상의 인스턴스를 사용 하 여 클래스를 지정 하는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="19725-107">[in] An array of class IDs, where each ID specifies a class with one or more instances.</span></span>  
  
 `cObjects`  
 <span data-ttu-id="19725-108">[in] 각 정수에 해당 클래스의 인스턴스 수를 지정 하는 위치, 정수의 배열을 `classIds` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="19725-108">[in] An array of integers, where each integer specifies the number of instances for the corresponding class in the `classIds` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19725-109">설명</span><span class="sxs-lookup"><span data-stu-id="19725-109">Remarks</span></span>  
 <span data-ttu-id="19725-110">합니다 `classIds` 고 `cObjects` 배열은 병렬 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="19725-110">The `classIds` and `cObjects` arrays are parallel arrays.</span></span> <span data-ttu-id="19725-111">예를 들어 `classIds[i]` 고 `cObjects[i]` 동일한 클래스를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="19725-111">For example, `classIds[i]` and `cObjects[i]` reference the same class.</span></span> <span data-ttu-id="19725-112">이전 가비지 수집 이후 클래스의 인스턴스를 만든 경우 클래스는 생략 됩니다.</span><span class="sxs-lookup"><span data-stu-id="19725-112">If no instance of a class has been created since the previous garbage collection, the class is omitted.</span></span> <span data-ttu-id="19725-113">`ObjectsAllocatedByClass` 콜백 대형 개체 힙에 할당 된 개체를 보고 하지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="19725-113">The `ObjectsAllocatedByClass` callback will not report objects allocated in the large object heap.</span></span>  
  
 <span data-ttu-id="19725-114">숫자에서 보고 `ObjectsAllocatedByClass` 만 예상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="19725-114">The numbers reported by `ObjectsAllocatedByClass` are only estimates.</span></span> <span data-ttu-id="19725-115">정확한 개수에 대 한 사용 [icorprofilercallback:: Objectallocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="19725-115">For exact counts, use [ICorProfilerCallback::ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).</span></span>  
  
 <span data-ttu-id="19725-116">합니다 `classIds` 배열의 경우 하나 이상의 null 항목을 포함할 수 있습니다 해당 `cObjects` 언로드하는 배열 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19725-116">The `classIds` array may contain one or more null entries if the corresponding `cObjects` array has types that are unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19725-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="19725-117">Requirements</span></span>  
 <span data-ttu-id="19725-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="19725-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19725-119">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="19725-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="19725-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19725-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19725-121">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19725-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19725-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="19725-122">See also</span></span>

- [<span data-ttu-id="19725-123">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="19725-123">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
