---
description: '자세히 알아보기: ICorProfilerCallback:: ClassUnloadStarted 메서드'
title: ICorProfilerCallback::ClassUnloadStarted 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassUnloadStarted
helpviewer_keywords:
- ClassUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ClassUnloadStarted method [.NET Framework profiling]
ms.assetid: bc93bead-f3a9-415c-b919-ddd3ca80facc
topic_type:
- apiref
ms.openlocfilehash: 91de255b2214ad0c6ce6911d9533df593142a191
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760679"
---
# <a name="icorprofilercallbackclassunloadstarted-method"></a><span data-ttu-id="09584-103">ICorProfilerCallback::ClassUnloadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="09584-103">ICorProfilerCallback::ClassUnloadStarted Method</span></span>

<span data-ttu-id="09584-104">클래스가 언로드되고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="09584-104">Notifies the profiler that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09584-105">구문</span><span class="sxs-lookup"><span data-stu-id="09584-105">Syntax</span></span>  
  
```cpp  
HRESULT ClassUnloadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09584-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="09584-106">Parameters</span></span>

<span data-ttu-id="09584-107">`classId` 진행 언로드될 클래스를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="09584-107">`classId` [in] Identifies the class that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="09584-108">설명</span><span class="sxs-lookup"><span data-stu-id="09584-108">Remarks</span></span>  

 <span data-ttu-id="09584-109">메서드가 반환 된 후에는 값이 `classId` 유효 하지 않습니다 .이는 `ClassUnloadStarted` 프로파일러에서이 클래스에 대 한 정보를 가져올 수 있는 마지막 기회입니다.</span><span class="sxs-lookup"><span data-stu-id="09584-109">The value of `classId` is not valid for an information request after the `ClassUnloadStarted` method returns — this is the profiler's last chance to obtain information about this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09584-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="09584-110">Requirements</span></span>  

 <span data-ttu-id="09584-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09584-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09584-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="09584-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="09584-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09584-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09584-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09584-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09584-115">참조</span><span class="sxs-lookup"><span data-stu-id="09584-115">See also</span></span>

- [<span data-ttu-id="09584-116">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="09584-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="09584-117">ClassUnloadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="09584-117">ClassUnloadFinished Method</span></span>](icorprofilercallback-classunloadfinished-method.md)
