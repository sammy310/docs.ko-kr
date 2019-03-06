---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7ed5debad7ef6722206daac98aecd7db11155a58
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57469289"
---
# <a name="icorprofilercallbackassemblyunloadfinished-method"></a><span data-ttu-id="2dabd-102">ICorProfilerCallback::AssemblyUnloadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="2dabd-102">ICorProfilerCallback::AssemblyUnloadFinished Method</span></span>
<span data-ttu-id="2dabd-103">어셈블리 로드 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="2dabd-103">Notifies the profiler that an assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2dabd-104">구문</span><span class="sxs-lookup"><span data-stu-id="2dabd-104">Syntax</span></span>  
  
```  
HRESULT AssemblyUnloadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2dabd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2dabd-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="2dabd-106">[in] 언로드되고 하는 어셈블리를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabd-106">[in] Identifies the assembly that is being unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="2dabd-107">[in] 어셈블리 로드 되었는지 여부를 하지 성공적으로 나타내는 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="2dabd-107">[in] An HRESULT that indicates whether the assembly was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2dabd-108">설명</span><span class="sxs-lookup"><span data-stu-id="2dabd-108">Remarks</span></span>  
 <span data-ttu-id="2dabd-109">값 `assemblyId` 후 정보 요청에 대해 올바르지 않습니다 합니다 [icorprofilercallback:: Assemblyunloadstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md) 메서드 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabd-109">The value of `assemblyId` is not valid for an information request after the [ICorProfilerCallback::AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="2dabd-110">일부 어셈블리 언로드 후 계속 사용할 수는 `AssemblyUnloadFinished` 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabd-110">Some parts of unloading the assembly might continue after the `AssemblyUnloadFinished` callback.</span></span> <span data-ttu-id="2dabd-111">오류 HRESULT에서 `hrStatus` 오류가 발생 했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2dabd-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="2dabd-112">그러나 성공 HRESULT에서 `hrStatus` 어셈블리 언로드에 대 한 첫 번째 부분 성공 했다는 것만 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2dabd-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2dabd-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2dabd-113">Requirements</span></span>  
 <span data-ttu-id="2dabd-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2dabd-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2dabd-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2dabd-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2dabd-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2dabd-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2dabd-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2dabd-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dabd-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="2dabd-118">See also</span></span>
- [<span data-ttu-id="2dabd-119">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2dabd-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
