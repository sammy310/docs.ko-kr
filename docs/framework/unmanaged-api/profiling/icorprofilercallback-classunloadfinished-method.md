---
description: '자세히 알아보기: ICorProfilerCallback:: ClassUnloadFinished 메서드'
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
ms.openlocfilehash: 7d4fd1c85d496b7adea0096b03520a14c2fab11c
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759255"
---
# <a name="icorprofilercallbackclassunloadfinished-method"></a><span data-ttu-id="4afd0-103">ICorProfilerCallback::ClassUnloadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="4afd0-103">ICorProfilerCallback::ClassUnloadFinished Method</span></span>

<span data-ttu-id="4afd0-104">클래스의 언로드가 완료 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="4afd0-104">Notifies the profiler that a class has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4afd0-105">구문</span><span class="sxs-lookup"><span data-stu-id="4afd0-105">Syntax</span></span>  
  
```cpp  
HRESULT ClassUnloadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4afd0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4afd0-106">Parameters</span></span>

<span data-ttu-id="4afd0-107">`classId` 진행 언로드된 클래스를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="4afd0-107">`classId` [in] Identifies the class that was unloaded.</span></span>

<span data-ttu-id="4afd0-108">`hrStatus` 진행 클래스가 성공적으로 언로드 되었는지 여부를 나타내는 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="4afd0-108">`hrStatus` [in] An HRESULT that indicates whether the class was unloaded successfully.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="4afd0-109">설명</span><span class="sxs-lookup"><span data-stu-id="4afd0-109">Remarks</span></span>  

 <span data-ttu-id="4afd0-110">클래스를 언로드하는 일부 부분은 콜백 후에도 계속 될 수 있습니다 `ClassUnloadFinished` .</span><span class="sxs-lookup"><span data-stu-id="4afd0-110">Some parts of unloading the class might continue after the `ClassUnloadFinished` callback.</span></span> <span data-ttu-id="4afd0-111">의 오류 HRESULT는 `hrStatus` 오류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4afd0-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="4afd0-112">그러나의 성공 HRESULT는 `hrStatus` 클래스를 언로드하는 첫 번째 부분만 성공 했다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4afd0-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4afd0-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4afd0-113">Requirements</span></span>  

 <span data-ttu-id="4afd0-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4afd0-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4afd0-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4afd0-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4afd0-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4afd0-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4afd0-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4afd0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4afd0-118">참조</span><span class="sxs-lookup"><span data-stu-id="4afd0-118">See also</span></span>

- [<span data-ttu-id="4afd0-119">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4afd0-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="4afd0-120">ClassUnloadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="4afd0-120">ClassUnloadStarted Method</span></span>](icorprofilercallback-classunloadstarted-method.md)
