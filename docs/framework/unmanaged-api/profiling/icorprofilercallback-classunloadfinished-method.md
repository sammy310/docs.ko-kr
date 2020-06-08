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
ms.openlocfilehash: 14eb90c707618796d6d62ed2ec5710ceba31ba6c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500379"
---
# <a name="icorprofilercallbackclassunloadfinished-method"></a><span data-ttu-id="240bd-102">ICorProfilerCallback::ClassUnloadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="240bd-102">ICorProfilerCallback::ClassUnloadFinished Method</span></span>
<span data-ttu-id="240bd-103">클래스의 언로드가 완료 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="240bd-103">Notifies the profiler that a class has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="240bd-104">구문</span><span class="sxs-lookup"><span data-stu-id="240bd-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassUnloadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="240bd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="240bd-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="240bd-106">\[in] 언로드된 클래스를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="240bd-106">\[in] Identifies the class that was unloaded.</span></span>

- `hrStatus`

  <span data-ttu-id="240bd-107">\[in] 클래스가 성공적으로 언로드 되었는지 여부를 나타내는 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="240bd-107">\[in] An HRESULT that indicates whether the class was unloaded successfully.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="240bd-108">설명</span><span class="sxs-lookup"><span data-stu-id="240bd-108">Remarks</span></span>  
 <span data-ttu-id="240bd-109">클래스를 언로드하는 일부 부분은 콜백 후에도 계속 될 수 있습니다 `ClassUnloadFinished` .</span><span class="sxs-lookup"><span data-stu-id="240bd-109">Some parts of unloading the class might continue after the `ClassUnloadFinished` callback.</span></span> <span data-ttu-id="240bd-110">의 오류 HRESULT는 `hrStatus` 오류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="240bd-110">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="240bd-111">그러나의 성공 HRESULT는 `hrStatus` 클래스를 언로드하는 첫 번째 부분만 성공 했다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="240bd-111">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="240bd-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="240bd-112">Requirements</span></span>  
 <span data-ttu-id="240bd-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="240bd-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="240bd-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="240bd-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="240bd-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="240bd-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="240bd-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="240bd-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="240bd-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="240bd-117">See also</span></span>

- [<span data-ttu-id="240bd-118">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="240bd-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="240bd-119">ClassUnloadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="240bd-119">ClassUnloadStarted Method</span></span>](icorprofilercallback-classunloadstarted-method.md)
