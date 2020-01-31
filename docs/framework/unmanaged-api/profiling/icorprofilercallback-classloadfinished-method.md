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
ms.openlocfilehash: e0ff90f99c1127b5a4626f47514ba7099b5d48af
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866600"
---
# <a name="icorprofilercallbackclassloadfinished-method"></a><span data-ttu-id="a188a-102">ICorProfilerCallback::ClassLoadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="a188a-102">ICorProfilerCallback::ClassLoadFinished Method</span></span>
<span data-ttu-id="a188a-103">클래스의 로드가 완료 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="a188a-103">Notifies the profiler that a class has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a188a-104">구문</span><span class="sxs-lookup"><span data-stu-id="a188a-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassLoadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a188a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a188a-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="a188a-106">\[in] 로드 된 클래스를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="a188a-106">\[in] Identifies the class that was loaded.</span></span>

- `hrStatus`

  <span data-ttu-id="a188a-107">\[] 클래스가 성공적으로 로드 되었는지 여부를 나타내는 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="a188a-107">\[in] An HRESULT that indicates whether the class loaded successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="a188a-108">주의</span><span class="sxs-lookup"><span data-stu-id="a188a-108">Remarks</span></span>  
 <span data-ttu-id="a188a-109">`classId` 값은 `ClassLoadFinished` 메서드를 호출할 때까지 정보 요청에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a188a-109">The value of `classId` is not valid for an information request until the `ClassLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="a188a-110">클래스 로드의 일부 부분은 `ClassLoadFinished` 콜백 후에도 계속 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a188a-110">Some parts of loading the class might continue after the `ClassLoadFinished` callback.</span></span> <span data-ttu-id="a188a-111">`hrStatus` 오류 HRESULT는 오류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a188a-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="a188a-112">그러나 `hrStatus`의 성공 HRESULT는 클래스를 로드 하는 첫 번째 부분이 성공 했다는 것만 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a188a-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a188a-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a188a-113">Requirements</span></span>  
 <span data-ttu-id="a188a-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a188a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a188a-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a188a-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a188a-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a188a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a188a-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a188a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a188a-118">참조</span><span class="sxs-lookup"><span data-stu-id="a188a-118">See also</span></span>

- [<span data-ttu-id="a188a-119">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a188a-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="a188a-120">ClassLoadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="a188a-120">ClassLoadStarted Method</span></span>](icorprofilercallback-classloadstarted-method.md)
