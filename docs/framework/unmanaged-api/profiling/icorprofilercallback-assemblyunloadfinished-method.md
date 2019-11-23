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
ms.openlocfilehash: 01404d23707be90b6b15cf741632400d49f164de
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445143"
---
# <a name="icorprofilercallbackassemblyunloadfinished-method"></a><span data-ttu-id="612e7-102">ICorProfilerCallback::AssemblyUnloadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="612e7-102">ICorProfilerCallback::AssemblyUnloadFinished Method</span></span>
<span data-ttu-id="612e7-103">Notifies the profiler that an assembly has been unloaded.</span><span class="sxs-lookup"><span data-stu-id="612e7-103">Notifies the profiler that an assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="612e7-104">구문</span><span class="sxs-lookup"><span data-stu-id="612e7-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyUnloadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="612e7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="612e7-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="612e7-106">[in] Identifies the assembly that is being unloaded.</span><span class="sxs-lookup"><span data-stu-id="612e7-106">[in] Identifies the assembly that is being unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="612e7-107">[in] An HRESULT that indicates whether the assembly was unloaded successfully.</span><span class="sxs-lookup"><span data-stu-id="612e7-107">[in] An HRESULT that indicates whether the assembly was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="612e7-108">주의</span><span class="sxs-lookup"><span data-stu-id="612e7-108">Remarks</span></span>  
 <span data-ttu-id="612e7-109">The value of `assemblyId` is not valid for an information request after the [ICorProfilerCallback::AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md) method returns.</span><span class="sxs-lookup"><span data-stu-id="612e7-109">The value of `assemblyId` is not valid for an information request after the [ICorProfilerCallback::AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="612e7-110">Some parts of unloading the assembly might continue after the `AssemblyUnloadFinished` callback.</span><span class="sxs-lookup"><span data-stu-id="612e7-110">Some parts of unloading the assembly might continue after the `AssemblyUnloadFinished` callback.</span></span> <span data-ttu-id="612e7-111">A failure HRESULT in `hrStatus` indicates a failure.</span><span class="sxs-lookup"><span data-stu-id="612e7-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="612e7-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the assembly has succeeded.</span><span class="sxs-lookup"><span data-stu-id="612e7-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="612e7-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="612e7-113">Requirements</span></span>  
 <span data-ttu-id="612e7-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="612e7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="612e7-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="612e7-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="612e7-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="612e7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="612e7-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="612e7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="612e7-118">참조</span><span class="sxs-lookup"><span data-stu-id="612e7-118">See also</span></span>

- [<span data-ttu-id="612e7-119">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="612e7-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
