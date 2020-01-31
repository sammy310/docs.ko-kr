---
title: ICorProfilerCallback::ClassUnloadFinished 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassUnloadFinished
helpviewer_keywords:
- ICorProfilerCallback::ClassUnloadFinished method [.NET Framework profiling]
- ClassUnloadFinished method [.NET Framework profiling]
ms.assetid: 55674b68-678a-4747-ae06-4e91519c7305
topic_type:
- apiref
ms.openlocfilehash: 5d9474f78dd8b999a37f60e0698cfd04240b897a
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866574"
---
# <a name="icorprofilercallbackclassunloadfinished-method"></a><span data-ttu-id="1fe02-102">ICorProfilerCallback::ClassUnloadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="1fe02-102">ICorProfilerCallback::ClassUnloadFinished Method</span></span>
<span data-ttu-id="1fe02-103">클래스의 언로드가 완료 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="1fe02-103">Notifies the profiler that a class has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fe02-104">구문</span><span class="sxs-lookup"><span data-stu-id="1fe02-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassUnloadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1fe02-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1fe02-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="1fe02-106">\[in]은 언로드된 클래스를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="1fe02-106">\[in] Identifies the class that was unloaded.</span></span>

- `hrStatus`

  <span data-ttu-id="1fe02-107">\[] 클래스가 성공적으로 언로드 되었는지 여부를 나타내는 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="1fe02-107">\[in] An HRESULT that indicates whether the class was unloaded successfully.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="1fe02-108">주의</span><span class="sxs-lookup"><span data-stu-id="1fe02-108">Remarks</span></span>  
 <span data-ttu-id="1fe02-109">클래스를 언로드하는 일부 부분은 `ClassUnloadFinished` 콜백 후에도 계속 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fe02-109">Some parts of unloading the class might continue after the `ClassUnloadFinished` callback.</span></span> <span data-ttu-id="1fe02-110">`hrStatus` 오류 HRESULT는 오류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1fe02-110">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="1fe02-111">그러나 `hrStatus`의 성공 HRESULT는 클래스를 언로드하는 첫 번째 부분이 성공 했다는 것만 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1fe02-111">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fe02-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1fe02-112">Requirements</span></span>  
 <span data-ttu-id="1fe02-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1fe02-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1fe02-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1fe02-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1fe02-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1fe02-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1fe02-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fe02-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fe02-117">참조</span><span class="sxs-lookup"><span data-stu-id="1fe02-117">See also</span></span>

- [<span data-ttu-id="1fe02-118">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1fe02-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="1fe02-119">ClassUnloadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="1fe02-119">ClassUnloadStarted Method</span></span>](icorprofilercallback-classunloadstarted-method.md)
