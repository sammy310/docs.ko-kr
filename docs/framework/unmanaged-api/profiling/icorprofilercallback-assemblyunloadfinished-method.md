---
description: '자세히 알아보기: ICorProfilerCallback:: AssemblyUnloadFinished 메서드'
title: ICorProfilerCallback::AssemblyUnloadFinished 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyUnloadFinished
helpviewer_keywords:
- AssemblyUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::AssemblyUnloadFinished method [.NET Framework profiling]
ms.assetid: 53fca564-84b1-44d4-9e21-17a492d2aae7
topic_type:
- apiref
ms.openlocfilehash: 30d6bd805a1466d6a65728b22f677ba00e09ffb6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99648027"
---
# <a name="icorprofilercallbackassemblyunloadfinished-method"></a><span data-ttu-id="2254c-103">ICorProfilerCallback::AssemblyUnloadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="2254c-103">ICorProfilerCallback::AssemblyUnloadFinished Method</span></span>

<span data-ttu-id="2254c-104">어셈블리가 언로드 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="2254c-104">Notifies the profiler that an assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2254c-105">구문</span><span class="sxs-lookup"><span data-stu-id="2254c-105">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyUnloadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2254c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2254c-106">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="2254c-107">\[in]은 언로드되고 있는 어셈블리를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="2254c-107">\[in] Identifies the assembly that is being unloaded.</span></span>

- `hrStatus`

  <span data-ttu-id="2254c-108">\[in] 어셈블리가 성공적으로 언로드 되었는지 여부를 나타내는 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="2254c-108">\[in] An HRESULT that indicates whether the assembly was unloaded successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="2254c-109">설명</span><span class="sxs-lookup"><span data-stu-id="2254c-109">Remarks</span></span>  

 <span data-ttu-id="2254c-110">`assemblyId` [ICorProfilerCallback:: AssemblyUnloadStarted](icorprofilercallback-assemblyunloadstarted-method.md) 메서드가 반환 된 후에는 값이 정보 요청에 적합 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2254c-110">The value of `assemblyId` is not valid for an information request after the [ICorProfilerCallback::AssemblyUnloadStarted](icorprofilercallback-assemblyunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="2254c-111">어셈블리를 언로드하는 일부 부분은 콜백 후에도 계속 될 수 있습니다 `AssemblyUnloadFinished` .</span><span class="sxs-lookup"><span data-stu-id="2254c-111">Some parts of unloading the assembly might continue after the `AssemblyUnloadFinished` callback.</span></span> <span data-ttu-id="2254c-112">의 오류 HRESULT는 `hrStatus` 오류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2254c-112">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="2254c-113">그러나의 성공 HRESULT는 `hrStatus` 어셈블리 언로드의 첫 번째 부분만 성공 했다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2254c-113">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2254c-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2254c-114">Requirements</span></span>  

 <span data-ttu-id="2254c-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2254c-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2254c-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2254c-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2254c-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2254c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2254c-118">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2254c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2254c-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2254c-119">See also</span></span>

- [<span data-ttu-id="2254c-120">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2254c-120">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
