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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f613842c12b50b8a58aac1b71bf2f3c53aaf961f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61914487"
---
# <a name="icorprofilercallback2garbagecollectionfinished-method"></a><span data-ttu-id="07568-102">ICorProfilerCallback2::GarbageCollectionFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="07568-102">ICorProfilerCallback2::GarbageCollectionFinished Method</span></span>
<span data-ttu-id="07568-103">가비지 수집이 완료 되 고에 대 한 모든 가비지 컬렉션 콜백이 실행 되었습니다 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="07568-103">Notifies the profiler that garbage collection has completed and all garbage collection callbacks have been issued for it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07568-104">구문</span><span class="sxs-lookup"><span data-stu-id="07568-104">Syntax</span></span>  
  
```  
HRESULT GarbageCollectionFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="07568-105">설명</span><span class="sxs-lookup"><span data-stu-id="07568-105">Remarks</span></span>  
 <span data-ttu-id="07568-106">최종 위치로 개체를 검사 하는 프로파일러가 안전 때는 `GarbageCollectionFinished` 메서드가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07568-106">It is safe for the profiler to inspect objects in their final locations when the `GarbageCollectionFinished` method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07568-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="07568-107">Requirements</span></span>  
 <span data-ttu-id="07568-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="07568-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07568-109">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="07568-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="07568-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="07568-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="07568-111">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07568-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07568-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="07568-112">See also</span></span>

- [<span data-ttu-id="07568-113">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="07568-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="07568-114">ICorProfilerCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="07568-114">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
