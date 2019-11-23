---
title: ICorProfilerCallback::ModuleAttachedToAssembly 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleAttachedToAssembly
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly
helpviewer_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly method [.NET Framework profiling]
- ModuleAttachedToAssembly method [.NET Framework profiling]
ms.assetid: b595798a-5d40-4cac-ab4f-911c61d2c5d2
topic_type:
- apiref
ms.openlocfilehash: d229b530062d759ab270612fa70b1799acbcadbe
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448078"
---
# <a name="icorprofilercallbackmoduleattachedtoassembly-method"></a><span data-ttu-id="60350-102">ICorProfilerCallback::ModuleAttachedToAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="60350-102">ICorProfilerCallback::ModuleAttachedToAssembly Method</span></span>
<span data-ttu-id="60350-103">Notifies the profiler that a module is being attached to its parent assembly.</span><span class="sxs-lookup"><span data-stu-id="60350-103">Notifies the profiler that a module is being attached to its parent assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60350-104">구문</span><span class="sxs-lookup"><span data-stu-id="60350-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleAttachedToAssembly(  
    [in] ModuleID   moduleId,  
    [in] AssemblyID AssemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60350-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="60350-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="60350-106">[in] The ID of the module that is being attached.</span><span class="sxs-lookup"><span data-stu-id="60350-106">[in] The ID of the module that is being attached.</span></span>  
  
 `AssemblyId`  
 <span data-ttu-id="60350-107">[in] The ID of the parent assembly to which the module is attached.</span><span class="sxs-lookup"><span data-stu-id="60350-107">[in] The ID of the parent assembly to which the module is attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60350-108">주의</span><span class="sxs-lookup"><span data-stu-id="60350-108">Remarks</span></span>  
 <span data-ttu-id="60350-109">A module can be loaded through an import address table (IAT), through a call to `LoadLibrary`, or through a metadata reference.</span><span class="sxs-lookup"><span data-stu-id="60350-109">A module can be loaded through an import address table (IAT), through a call to `LoadLibrary`, or through a metadata reference.</span></span> <span data-ttu-id="60350-110">As a result, the common language runtime (CLR) loader has multiple code paths for determining the assembly in which a module lives.</span><span class="sxs-lookup"><span data-stu-id="60350-110">As a result, the common language runtime (CLR) loader has multiple code paths for determining the assembly in which a module lives.</span></span> <span data-ttu-id="60350-111">Therefore, it is possible that after [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) is called, the module does not know what assembly it is in and getting the parent assembly ID is not possible.</span><span class="sxs-lookup"><span data-stu-id="60350-111">Therefore, it is possible that after [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) is called, the module does not know what assembly it is in and getting the parent assembly ID is not possible.</span></span> <span data-ttu-id="60350-112">The `ModuleAttachedToAssembly` method is called when the module is attached to its parent assembly and its parent assembly ID can be obtained.</span><span class="sxs-lookup"><span data-stu-id="60350-112">The `ModuleAttachedToAssembly` method is called when the module is attached to its parent assembly and its parent assembly ID can be obtained.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60350-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="60350-113">Requirements</span></span>  
 <span data-ttu-id="60350-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="60350-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60350-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="60350-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="60350-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60350-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60350-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60350-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60350-118">참조</span><span class="sxs-lookup"><span data-stu-id="60350-118">See also</span></span>

- [<span data-ttu-id="60350-119">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="60350-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
