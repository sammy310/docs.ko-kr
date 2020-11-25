---
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
ms.openlocfilehash: 1c154eee85811796321aea2647db1c8996997576
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700251"
---
# <a name="icorprofilercallbackclassunloadstarted-method"></a><span data-ttu-id="96063-102">ICorProfilerCallback::ClassUnloadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="96063-102">ICorProfilerCallback::ClassUnloadStarted Method</span></span>

<span data-ttu-id="96063-103">클래스가 언로드되고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="96063-103">Notifies the profiler that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96063-104">구문</span><span class="sxs-lookup"><span data-stu-id="96063-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassUnloadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="96063-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="96063-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="96063-106">\[in]은 언로드될 클래스를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="96063-106">\[in] Identifies the class that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="96063-107">설명</span><span class="sxs-lookup"><span data-stu-id="96063-107">Remarks</span></span>  

 <span data-ttu-id="96063-108">메서드가 반환 된 후에는 값이 `classId` 유효 하지 않습니다 .이는 `ClassUnloadStarted` 프로파일러에서이 클래스에 대 한 정보를 가져올 수 있는 마지막 기회입니다.</span><span class="sxs-lookup"><span data-stu-id="96063-108">The value of `classId` is not valid for an information request after the `ClassUnloadStarted` method returns — this is the profiler's last chance to obtain information about this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96063-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="96063-109">Requirements</span></span>  

 <span data-ttu-id="96063-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96063-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96063-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="96063-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="96063-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96063-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96063-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96063-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96063-114">참조</span><span class="sxs-lookup"><span data-stu-id="96063-114">See also</span></span>

- [<span data-ttu-id="96063-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="96063-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="96063-116">ClassUnloadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="96063-116">ClassUnloadFinished Method</span></span>](icorprofilercallback-classunloadfinished-method.md)
