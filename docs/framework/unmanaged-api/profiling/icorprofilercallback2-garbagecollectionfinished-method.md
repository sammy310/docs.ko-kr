---
title: ICorProfilerCallback2::GarbageCollectionFinished 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.GarbageCollectionFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::GarbageCollectionFinished
helpviewer_keywords:
- ICorProfilerCallback2::GarbageCollectionFinished method [.NET Framework profiling]
- GarbageCollectionFinished method [.NET Framework profiling]
ms.assetid: 1a5758ea-2354-43c0-92a3-32c9909d64e1
topic_type:
- apiref
ms.openlocfilehash: 47f25dbb1f88dbf580b096246016cd46f2d0d89c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499830"
---
# <a name="icorprofilercallback2garbagecollectionfinished-method"></a><span data-ttu-id="db442-102">ICorProfilerCallback2::GarbageCollectionFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="db442-102">ICorProfilerCallback2::GarbageCollectionFinished Method</span></span>
<span data-ttu-id="db442-103">가비지 수집이 완료 되었으며이에 대해 모든 가비지 수집 콜백이 실행 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="db442-103">Notifies the profiler that garbage collection has completed and all garbage collection callbacks have been issued for it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db442-104">구문</span><span class="sxs-lookup"><span data-stu-id="db442-104">Syntax</span></span>  
  
```cpp  
HRESULT GarbageCollectionFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="db442-105">설명</span><span class="sxs-lookup"><span data-stu-id="db442-105">Remarks</span></span>  
 <span data-ttu-id="db442-106">메서드가 호출 될 때 프로파일러에서 최종 위치의 개체를 검사 하는 것이 안전 합니다 `GarbageCollectionFinished` .</span><span class="sxs-lookup"><span data-stu-id="db442-106">It is safe for the profiler to inspect objects in their final locations when the `GarbageCollectionFinished` method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db442-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="db442-107">Requirements</span></span>  
 <span data-ttu-id="db442-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="db442-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db442-109">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="db442-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="db442-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db442-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db442-111">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db442-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db442-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="db442-112">See also</span></span>

- [<span data-ttu-id="db442-113">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="db442-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="db442-114">ICorProfilerCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="db442-114">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
