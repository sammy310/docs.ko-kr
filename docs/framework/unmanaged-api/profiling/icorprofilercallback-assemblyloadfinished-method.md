---
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
ms.openlocfilehash: 33b72c8d089e5b335069fe465987086dfa1243bc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445178"
---
# <a name="icorprofilercallbackassemblyloadfinished-method"></a><span data-ttu-id="83be8-102">ICorProfilerCallback::AssemblyLoadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="83be8-102">ICorProfilerCallback::AssemblyLoadFinished Method</span></span>
<span data-ttu-id="83be8-103">Notifies the profiler that an assembly has finished loading.</span><span class="sxs-lookup"><span data-stu-id="83be8-103">Notifies the profiler that an assembly has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83be8-104">구문</span><span class="sxs-lookup"><span data-stu-id="83be8-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyLoadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83be8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="83be8-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="83be8-106">[in] Identifies the assembly that was loaded.</span><span class="sxs-lookup"><span data-stu-id="83be8-106">[in] Identifies the assembly that was loaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="83be8-107">[in] An HRESULT that indicates whether the assembly finished loading successfully.</span><span class="sxs-lookup"><span data-stu-id="83be8-107">[in] An HRESULT that indicates whether the assembly finished loading successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83be8-108">주의</span><span class="sxs-lookup"><span data-stu-id="83be8-108">Remarks</span></span>  
 <span data-ttu-id="83be8-109">The value of `assemblyId` is not valid for an information request until the `AssemblyLoadFinished` method is called.</span><span class="sxs-lookup"><span data-stu-id="83be8-109">The value of `assemblyId` is not valid for an information request until the `AssemblyLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="83be8-110">Some parts of loading the assembly might continue after the `AssemblyLoadFinished` callback.</span><span class="sxs-lookup"><span data-stu-id="83be8-110">Some parts of loading the assembly might continue after the `AssemblyLoadFinished` callback.</span></span> <span data-ttu-id="83be8-111">A failure HRESULT in `hrStatus` indicates a failure.</span><span class="sxs-lookup"><span data-stu-id="83be8-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="83be8-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the assembly has succeeded.</span><span class="sxs-lookup"><span data-stu-id="83be8-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83be8-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="83be8-113">Requirements</span></span>  
 <span data-ttu-id="83be8-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83be8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83be8-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="83be8-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="83be8-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83be8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83be8-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83be8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83be8-118">참조</span><span class="sxs-lookup"><span data-stu-id="83be8-118">See also</span></span>

- [<span data-ttu-id="83be8-119">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="83be8-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
