---
title: ICorProfilerInfo::BeginInprocDebugging 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.BeginInprocDebugging
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::BeginInprocDebugging
helpviewer_keywords:
- BeginInprocDebugging method [.NET Framework profiling]
- ICorProfilerInfo::BeginInprocDebugging method [.NET Framework profiling]
ms.assetid: c5c82c69-99f8-4447-aee0-42cca0a5eb5c
topic_type:
- apiref
ms.openlocfilehash: fffc028c7706c86e8384483cc92ebad90b292861
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447743"
---
# <a name="icorprofilerinfobegininprocdebugging-method"></a><span data-ttu-id="3c85a-102">ICorProfilerInfo::BeginInprocDebugging 메서드</span><span class="sxs-lookup"><span data-stu-id="3c85a-102">ICorProfilerInfo::BeginInprocDebugging Method</span></span>
<span data-ttu-id="3c85a-103">Initializes in-process debugging support.</span><span class="sxs-lookup"><span data-stu-id="3c85a-103">Initializes in-process debugging support.</span></span> <span data-ttu-id="3c85a-104">This method is obsolete in the .NET Framework version 2.0.</span><span class="sxs-lookup"><span data-stu-id="3c85a-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c85a-105">구문</span><span class="sxs-lookup"><span data-stu-id="3c85a-105">Syntax</span></span>  
  
```cpp  
HRESULT BeginInprocDebugging(  
    [in]  BOOL   fThisThreadOnly,  
    [out] DWORD *pdwProfilerContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c85a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3c85a-106">Parameters</span></span>  
 `fThisThreadOnly`  
 <span data-ttu-id="3c85a-107">[in] Set this value to `true` to initialize debugging support for only the current thread; set it to `false` to initialize debugging support for all threads.</span><span class="sxs-lookup"><span data-stu-id="3c85a-107">[in] Set this value to `true` to initialize debugging support for only the current thread; set it to `false` to initialize debugging support for all threads.</span></span>  
  
 `pdwProfilerContext`  
 <span data-ttu-id="3c85a-108">[out] The pointer to a returned value that identifies the debugging session.</span><span class="sxs-lookup"><span data-stu-id="3c85a-108">[out] The pointer to a returned value that identifies the debugging session.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c85a-109">주의</span><span class="sxs-lookup"><span data-stu-id="3c85a-109">Remarks</span></span>  
 <span data-ttu-id="3c85a-110">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span><span class="sxs-lookup"><span data-stu-id="3c85a-110">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="3c85a-111">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span><span class="sxs-lookup"><span data-stu-id="3c85a-111">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="3c85a-112">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span><span class="sxs-lookup"><span data-stu-id="3c85a-112">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c85a-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3c85a-113">Requirements</span></span>  
 <span data-ttu-id="3c85a-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3c85a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c85a-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3c85a-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3c85a-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c85a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c85a-117">**.NET Framework Version:** 1.0</span><span class="sxs-lookup"><span data-stu-id="3c85a-117">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c85a-118">참조</span><span class="sxs-lookup"><span data-stu-id="3c85a-118">See also</span></span>

- [<span data-ttu-id="3c85a-119">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3c85a-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
