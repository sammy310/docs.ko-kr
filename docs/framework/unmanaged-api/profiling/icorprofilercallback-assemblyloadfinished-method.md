---
description: '자세히 알아보기: ICorProfilerCallback:: AssemblyLoadFinished 메서드'
title: ICorProfilerCallback::AssemblyLoadFinished 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyLoadFinished
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadFinished method [.NET Framework profiling]
- AssemblyLoadFinished method [.NET Framework profiling]
ms.assetid: 86d98f39-52e6-4c61-a625-9760f695ff12
topic_type:
- apiref
ms.openlocfilehash: 19c0871808455e64ad8a4eb002806a87030f7882
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99648040"
---
# <a name="icorprofilercallbackassemblyloadfinished-method"></a><span data-ttu-id="0153d-103">ICorProfilerCallback::AssemblyLoadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="0153d-103">ICorProfilerCallback::AssemblyLoadFinished Method</span></span>

<span data-ttu-id="0153d-104">어셈블리의 로드가 완료 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="0153d-104">Notifies the profiler that an assembly has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0153d-105">구문</span><span class="sxs-lookup"><span data-stu-id="0153d-105">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyLoadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0153d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0153d-106">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="0153d-107">\[in] 로드 된 어셈블리를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="0153d-107">\[in] Identifies the assembly that was loaded.</span></span>

- `hrStatus`

  <span data-ttu-id="0153d-108">\[in] 어셈블리의 로드가 성공적으로 완료 되었는지 여부를 나타내는 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="0153d-108">\[in] An HRESULT that indicates whether the assembly finished loading successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="0153d-109">설명</span><span class="sxs-lookup"><span data-stu-id="0153d-109">Remarks</span></span>  

 <span data-ttu-id="0153d-110">`assemblyId`메서드를 호출할 때까지 정보 요청에 대 한 값이 유효 하지 않습니다 `AssemblyLoadFinished` .</span><span class="sxs-lookup"><span data-stu-id="0153d-110">The value of `assemblyId` is not valid for an information request until the `AssemblyLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="0153d-111">어셈블리를 로드 하는 일부 부분은 콜백 후에도 계속 될 수 있습니다 `AssemblyLoadFinished` .</span><span class="sxs-lookup"><span data-stu-id="0153d-111">Some parts of loading the assembly might continue after the `AssemblyLoadFinished` callback.</span></span> <span data-ttu-id="0153d-112">의 오류 HRESULT는 `hrStatus` 오류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0153d-112">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="0153d-113">그러나의 성공 HRESULT는 어셈블리를 로드 하는 `hrStatus` 첫 번째 부분이 성공 했다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0153d-113">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0153d-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0153d-114">Requirements</span></span>  

 <span data-ttu-id="0153d-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0153d-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0153d-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0153d-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0153d-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0153d-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0153d-118">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0153d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0153d-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0153d-119">See also</span></span>

- [<span data-ttu-id="0153d-120">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0153d-120">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
