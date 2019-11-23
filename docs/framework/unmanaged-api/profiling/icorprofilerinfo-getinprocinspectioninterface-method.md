---
title: ICorProfilerInfo::GetInprocInspectionInterface 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetInprocInspectionInterface
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetInprocInspectionInterface
helpviewer_keywords:
- GetInprocInspectionInterface method [.NET Framework profiling]
- ICorProfilerInfo::GetInprocInspectionInterface method [.NET Framework profiling]
ms.assetid: 22a92d1d-8849-4af6-8304-ecc53dd1d289
topic_type:
- apiref
ms.openlocfilehash: d3fcd859fb11f6a0c660751f16fa175e19e9d03b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439001"
---
# <a name="icorprofilerinfogetinprocinspectioninterface-method"></a><span data-ttu-id="7d396-102">ICorProfilerInfo::GetInprocInspectionInterface 메서드</span><span class="sxs-lookup"><span data-stu-id="7d396-102">ICorProfilerInfo::GetInprocInspectionInterface Method</span></span>
<span data-ttu-id="7d396-103">Gets an object that can be queried for an "ICorDebugProcess" interface.</span><span class="sxs-lookup"><span data-stu-id="7d396-103">Gets an object that can be queried for an "ICorDebugProcess" interface.</span></span> <span data-ttu-id="7d396-104">This method is obsolete in the .NET Framework version 2.0.</span><span class="sxs-lookup"><span data-stu-id="7d396-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d396-105">구문</span><span class="sxs-lookup"><span data-stu-id="7d396-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInprocInspectionInterface(  
    [out] IUnknown **ppicd);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d396-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7d396-106">Parameters</span></span>  
 `ppicd`  
 <span data-ttu-id="7d396-107">[out](/cpp/atl/iunknown) object that can be queried for an `ICorDebugProcess` interface.</span><span class="sxs-lookup"><span data-stu-id="7d396-107">[out](/cpp/atl/iunknown) object that can be queried for an `ICorDebugProcess` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d396-108">주의</span><span class="sxs-lookup"><span data-stu-id="7d396-108">Remarks</span></span>  
 <span data-ttu-id="7d396-109">The common language runtime (CLR) debugging API supported limited in-process debugging in the .NET Framework version 1.0.</span><span class="sxs-lookup"><span data-stu-id="7d396-109">The common language runtime (CLR) debugging API supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="7d396-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span><span class="sxs-lookup"><span data-stu-id="7d396-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="7d396-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span><span class="sxs-lookup"><span data-stu-id="7d396-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d396-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7d396-112">Requirements</span></span>  
 <span data-ttu-id="7d396-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d396-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d396-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7d396-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7d396-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d396-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d396-116">**.NET Framework Version:** 1.0</span><span class="sxs-lookup"><span data-stu-id="7d396-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d396-117">참조</span><span class="sxs-lookup"><span data-stu-id="7d396-117">See also</span></span>

- [<span data-ttu-id="7d396-118">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7d396-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
