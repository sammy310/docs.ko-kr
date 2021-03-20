---
description: '자세히 알아보기: ICorProfilerCallback:: ClassLoadFinished 메서드'
title: ICorProfilerCallback::ClassLoadFinished 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassLoadFinished
helpviewer_keywords:
- ClassLoadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ClassLoadFinished method [.NET Framework profiling]
ms.assetid: 3dd80fbe-d62d-4d4d-acf8-5b7d0efe607e
topic_type:
- apiref
ms.openlocfilehash: 52fd26c1efaf9b85caeb5af7184ae70e1d29b9ff
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760221"
---
# <a name="icorprofilercallbackclassloadfinished-method"></a><span data-ttu-id="22237-103">ICorProfilerCallback::ClassLoadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="22237-103">ICorProfilerCallback::ClassLoadFinished Method</span></span>

<span data-ttu-id="22237-104">클래스의 로드가 완료 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="22237-104">Notifies the profiler that a class has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22237-105">구문</span><span class="sxs-lookup"><span data-stu-id="22237-105">Syntax</span></span>  
  
```cpp  
HRESULT ClassLoadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22237-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="22237-106">Parameters</span></span>

<span data-ttu-id="22237-107">`classId` 진행 로드 된 클래스를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="22237-107">`classId` [in] Identifies the class that was loaded.</span></span>

<span data-ttu-id="22237-108">`hrStatus` 진행 클래스가 성공적으로 로드 되었는지 여부를 나타내는 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="22237-108">`hrStatus` [in] An HRESULT that indicates whether the class loaded successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="22237-109">설명</span><span class="sxs-lookup"><span data-stu-id="22237-109">Remarks</span></span>  

 <span data-ttu-id="22237-110">`classId`메서드를 호출할 때까지 정보 요청에 대 한 값이 유효 하지 않습니다 `ClassLoadFinished` .</span><span class="sxs-lookup"><span data-stu-id="22237-110">The value of `classId` is not valid for an information request until the `ClassLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="22237-111">클래스 로드의 일부 부분은 콜백 후에도 계속 될 수 있습니다 `ClassLoadFinished` .</span><span class="sxs-lookup"><span data-stu-id="22237-111">Some parts of loading the class might continue after the `ClassLoadFinished` callback.</span></span> <span data-ttu-id="22237-112">의 오류 HRESULT는 `hrStatus` 오류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="22237-112">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="22237-113">그러나의 성공 HRESULT는 클래스를 로드 하는 `hrStatus` 첫 번째 부분이 성공 했다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="22237-113">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22237-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="22237-114">Requirements</span></span>  

 <span data-ttu-id="22237-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="22237-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22237-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="22237-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="22237-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22237-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22237-118">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22237-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22237-119">참조</span><span class="sxs-lookup"><span data-stu-id="22237-119">See also</span></span>

- [<span data-ttu-id="22237-120">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="22237-120">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="22237-121">ClassLoadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="22237-121">ClassLoadStarted Method</span></span>](icorprofilercallback-classloadstarted-method.md)
