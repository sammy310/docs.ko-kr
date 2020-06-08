---
title: ICorProfilerCallback2::HandleCreated 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.HandleCreated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::HandleCreated
helpviewer_keywords:
- HandleCreated method [.NET Framework profiling]
- ICorProfilerCallback2::HandleCreated method [.NET Framework profiling]
ms.assetid: 6bbb7786-7c38-490f-9834-91aa2795c355
topic_type:
- apiref
ms.openlocfilehash: 772f0c00bb850e35a6f5bf7fa4df2b3052999df5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499794"
---
# <a name="icorprofilercallback2handlecreated-method"></a><span data-ttu-id="c7cda-102">ICorProfilerCallback2::HandleCreated 메서드</span><span class="sxs-lookup"><span data-stu-id="c7cda-102">ICorProfilerCallback2::HandleCreated Method</span></span>
<span data-ttu-id="c7cda-103">가비지 수집 핸들이 생성 되었음을 코드 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="c7cda-103">Notifies the code profiler that a garbage collection handle has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7cda-104">구문</span><span class="sxs-lookup"><span data-stu-id="c7cda-104">Syntax</span></span>  
  
```cpp  
HRESULT HandleCreated(  
    [in] GCHandleID handleId,  
    [in] ObjectID initialObjectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7cda-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c7cda-105">Parameters</span></span>  
 `handleId`  
 <span data-ttu-id="c7cda-106">진행 가비지 컬렉션에 대 한 핸들의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c7cda-106">[in] The ID of the handle for the garbage collection.</span></span>  
  
 `initialObjectId`  
 <span data-ttu-id="c7cda-107">진행 가비지 수집 핸들을 만든 개체의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c7cda-107">[in] The ID of the object for which the garbage collection handle was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7cda-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c7cda-108">Requirements</span></span>  
 <span data-ttu-id="c7cda-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7cda-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7cda-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c7cda-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c7cda-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7cda-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7cda-112">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7cda-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7cda-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c7cda-113">See also</span></span>

- [<span data-ttu-id="c7cda-114">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c7cda-114">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="c7cda-115">ICorProfilerCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c7cda-115">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
