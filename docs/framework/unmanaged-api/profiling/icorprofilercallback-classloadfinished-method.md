---
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
ms.openlocfilehash: 4be2a50664b001e865b5ecdd9aabe8ba727b8c26
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500392"
---
# <a name="icorprofilercallbackclassloadfinished-method"></a><span data-ttu-id="f97ed-102">ICorProfilerCallback::ClassLoadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="f97ed-102">ICorProfilerCallback::ClassLoadFinished Method</span></span>
<span data-ttu-id="f97ed-103">클래스의 로드가 완료 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="f97ed-103">Notifies the profiler that a class has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f97ed-104">구문</span><span class="sxs-lookup"><span data-stu-id="f97ed-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassLoadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f97ed-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f97ed-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="f97ed-106">\[in] 로드 된 클래스를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="f97ed-106">\[in] Identifies the class that was loaded.</span></span>

- `hrStatus`

  <span data-ttu-id="f97ed-107">\[in] 클래스가 성공적으로 로드 되었는지 여부를 나타내는 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="f97ed-107">\[in] An HRESULT that indicates whether the class loaded successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="f97ed-108">설명</span><span class="sxs-lookup"><span data-stu-id="f97ed-108">Remarks</span></span>  
 <span data-ttu-id="f97ed-109">`classId`메서드를 호출할 때까지 정보 요청에 대 한 값이 유효 하지 않습니다 `ClassLoadFinished` .</span><span class="sxs-lookup"><span data-stu-id="f97ed-109">The value of `classId` is not valid for an information request until the `ClassLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="f97ed-110">클래스 로드의 일부 부분은 콜백 후에도 계속 될 수 있습니다 `ClassLoadFinished` .</span><span class="sxs-lookup"><span data-stu-id="f97ed-110">Some parts of loading the class might continue after the `ClassLoadFinished` callback.</span></span> <span data-ttu-id="f97ed-111">의 오류 HRESULT는 `hrStatus` 오류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f97ed-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="f97ed-112">그러나의 성공 HRESULT는 클래스를 로드 하는 `hrStatus` 첫 번째 부분이 성공 했다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f97ed-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f97ed-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f97ed-113">Requirements</span></span>  
 <span data-ttu-id="f97ed-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f97ed-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f97ed-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f97ed-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f97ed-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f97ed-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f97ed-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f97ed-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f97ed-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f97ed-118">See also</span></span>

- [<span data-ttu-id="f97ed-119">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f97ed-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="f97ed-120">ClassLoadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="f97ed-120">ClassLoadStarted Method</span></span>](icorprofilercallback-classloadstarted-method.md)
