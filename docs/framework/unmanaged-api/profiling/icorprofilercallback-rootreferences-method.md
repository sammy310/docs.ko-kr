---
title: ICorProfilerCallback::RootReferences 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RootReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RootReferences
helpviewer_keywords:
- RootReferences method [.NET Framework profiling]
- ICorProfilerCallback::RootReferences method [.NET Framework profiling]
ms.assetid: dbdf853b-d1a4-4828-8ef7-53d121d8e6ae
topic_type:
- apiref
ms.openlocfilehash: b587f30a01623c6e9806bcd9d01058a0880be239
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499911"
---
# <a name="icorprofilercallbackrootreferences-method"></a><span data-ttu-id="48557-102">ICorProfilerCallback::RootReferences 메서드</span><span class="sxs-lookup"><span data-stu-id="48557-102">ICorProfilerCallback::RootReferences Method</span></span>
<span data-ttu-id="48557-103">가비지 수집 후 루트 참조에 대 한 정보를 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="48557-103">Notifies the profiler with information about root references after garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48557-104">구문</span><span class="sxs-lookup"><span data-stu-id="48557-104">Syntax</span></span>  
  
```cpp  
HRESULT RootReferences(  
    [in] ULONG    cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="48557-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="48557-105">Parameters</span></span>  
 `cRootRefs`  
 <span data-ttu-id="48557-106">진행 배열에 있는 참조의 수 `rootRefIds` 입니다.</span><span class="sxs-lookup"><span data-stu-id="48557-106">[in] The number of references in the `rootRefIds` array.</span></span>  
  
 `rootRefIds`  
 <span data-ttu-id="48557-107">진행 스택의 개체 또는 정적 개체를 참조 하는 개체 Id의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="48557-107">[in] An array of object IDs that reference either a static object or an object on the stack.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48557-108">설명</span><span class="sxs-lookup"><span data-stu-id="48557-108">Remarks</span></span>  
 <span data-ttu-id="48557-109">`RootReferences`및 [ICorProfilerCallback2:: RootReferences2](icorprofilercallback2-rootreferences2-method.md) 를 모두 호출 하 여 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="48557-109">Both `RootReferences` and [ICorProfilerCallback2::RootReferences2](icorprofilercallback2-rootreferences2-method.md) are called to notify the profiler.</span></span> <span data-ttu-id="48557-110">일반적으로 전달 되는 정보는 `RootReferences2` 전달 되는의 상위 집합 이므로 프로파일러는 일반적으로 하나 또는 다른 하나를 구현 `RootReferences` 합니다.</span><span class="sxs-lookup"><span data-stu-id="48557-110">Profilers will normally implement one or the other, but not both, because the information passed in `RootReferences2` is a superset of that passed in `RootReferences`.</span></span>  
  
 <span data-ttu-id="48557-111">`rootRefIds`배열에 null 개체가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48557-111">It is possible for the `rootRefIds` array to contain a null object.</span></span> <span data-ttu-id="48557-112">예를 들어 스택에 선언 된 모든 개체 참조는 가비지 수집기에 의해 루트로 처리 되며 항상 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48557-112">For example, all object references declared on the stack are treated as roots by the garbage collector and will always be reported.</span></span>  
  
 <span data-ttu-id="48557-113">에서 반환 하는 개체 Id는 `RootReferences` 가비지 컬렉션이 이전 주소에서 새 주소로 개체를 이동 하는 중일 수 있기 때문에 콜백 자체 중에는 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="48557-113">The object IDs returned by `RootReferences` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects from old addresses to new addresses.</span></span> <span data-ttu-id="48557-114">따라서 프로파일러는 호출 하는 동안 개체 검사를 시도 하지 않아야 합니다 `RootReferences` .</span><span class="sxs-lookup"><span data-stu-id="48557-114">Therefore, profilers must not attempt to inspect objects during a `RootReferences` call.</span></span> <span data-ttu-id="48557-115">[ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) 를 호출 하면 모든 개체가 새 위치로 이동 되었으며 안전 하 게 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48557-115">When [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) is called, all objects have been moved to their new locations and can be safely inspected.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48557-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="48557-116">Requirements</span></span>  
 <span data-ttu-id="48557-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="48557-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48557-118">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="48557-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="48557-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48557-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48557-120">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48557-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48557-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="48557-121">See also</span></span>

- [<span data-ttu-id="48557-122">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="48557-122">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
