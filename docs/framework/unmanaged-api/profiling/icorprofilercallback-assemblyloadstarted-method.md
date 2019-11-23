---
title: ICorProfilerCallback::AssemblyLoadStarted 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyLoadStarted
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadStarted method [.NET Framework profiling]
- AssemblyLoadStarted method [.NET Framework profiling]
ms.assetid: 67e8209d-a0ca-4118-a6e6-c1ee0abc2221
topic_type:
- apiref
ms.openlocfilehash: 34744132442440ef160841db5a50bf75355f2410
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445163"
---
# <a name="icorprofilercallbackassemblyloadstarted-method"></a><span data-ttu-id="a7615-102">ICorProfilerCallback::AssemblyLoadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="a7615-102">ICorProfilerCallback::AssemblyLoadStarted Method</span></span>
<span data-ttu-id="a7615-103">Notifies the profiler that an assembly is being loaded.</span><span class="sxs-lookup"><span data-stu-id="a7615-103">Notifies the profiler that an assembly is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7615-104">구문</span><span class="sxs-lookup"><span data-stu-id="a7615-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyLoadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7615-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a7615-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="a7615-106">[in] Identifies the assembly that is being loaded.</span><span class="sxs-lookup"><span data-stu-id="a7615-106">[in] Identifies the assembly that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7615-107">주의</span><span class="sxs-lookup"><span data-stu-id="a7615-107">Remarks</span></span>  
 <span data-ttu-id="a7615-108">The value of `assemblyId` is not valid for an information request until the [ICorProfilerCallback::AssemblyLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md) method is called.</span><span class="sxs-lookup"><span data-stu-id="a7615-108">The value of `assemblyId` is not valid for an information request until the [ICorProfilerCallback::AssemblyLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7615-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a7615-109">Requirements</span></span>  
 <span data-ttu-id="a7615-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a7615-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7615-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a7615-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a7615-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7615-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7615-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7615-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7615-114">참조</span><span class="sxs-lookup"><span data-stu-id="a7615-114">See also</span></span>

- [<span data-ttu-id="a7615-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a7615-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
