---
title: ICorProfilerInfo::SetILFunctionBody 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerInfo::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method [.NET Framework profiling]
ms.assetid: b159c712-00f4-4fc7-a990-40bf9f642e8f
topic_type:
- apiref
ms.openlocfilehash: da81bd3e255898543c94d4ac64c6afbf39b6bdba
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449874"
---
# <a name="icorprofilerinfosetilfunctionbody-method"></a><span data-ttu-id="4ee47-102">ICorProfilerInfo::SetILFunctionBody 메서드</span><span class="sxs-lookup"><span data-stu-id="4ee47-102">ICorProfilerInfo::SetILFunctionBody Method</span></span>
<span data-ttu-id="4ee47-103">Replaces the body of the specified function in the specified module.</span><span class="sxs-lookup"><span data-stu-id="4ee47-103">Replaces the body of the specified function in the specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ee47-104">구문</span><span class="sxs-lookup"><span data-stu-id="4ee47-104">Syntax</span></span>  
  
```cpp  
HRESULT SetILFunctionBody(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodid,  
    [in] LPCBYTE     pbNewILMethodHeader);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ee47-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4ee47-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="4ee47-106">[in] The ID of the module in which the function resides.</span><span class="sxs-lookup"><span data-stu-id="4ee47-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `methodid`  
 <span data-ttu-id="4ee47-107">[in] The token of the function for which to replace the body.</span><span class="sxs-lookup"><span data-stu-id="4ee47-107">[in] The token of the function for which to replace the body.</span></span>  
  
 `pbNewILMethodHeader`  
 <span data-ttu-id="4ee47-108">[in] The new header for the function.</span><span class="sxs-lookup"><span data-stu-id="4ee47-108">[in] The new header for the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ee47-109">주의</span><span class="sxs-lookup"><span data-stu-id="4ee47-109">Remarks</span></span>  
 <span data-ttu-id="4ee47-110">The `SetILFunctionBody` method replaces the relative virtual address of the function in the metadata so that it points to the new function body, and adjusts any internal data structures as required.</span><span class="sxs-lookup"><span data-stu-id="4ee47-110">The `SetILFunctionBody` method replaces the relative virtual address of the function in the metadata so that it points to the new function body, and adjusts any internal data structures as required.</span></span>  
  
 <span data-ttu-id="4ee47-111">The `SetILFunctionBody` method can be called on only those functions that have never been compiled by a just-in-time (JIT) compiler.</span><span class="sxs-lookup"><span data-stu-id="4ee47-111">The `SetILFunctionBody` method can be called on only those functions that have never been compiled by a just-in-time (JIT) compiler.</span></span>  
  
 <span data-ttu-id="4ee47-112">Use the [ICorProfilerInfo::GetILFunctionBodyAllocator](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md) method to allocate space for the new method to ensure that the buffer is compatible.</span><span class="sxs-lookup"><span data-stu-id="4ee47-112">Use the [ICorProfilerInfo::GetILFunctionBodyAllocator](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md) method to allocate space for the new method to ensure that the buffer is compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ee47-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4ee47-113">Requirements</span></span>  
 <span data-ttu-id="4ee47-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ee47-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ee47-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4ee47-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4ee47-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ee47-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ee47-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ee47-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ee47-118">참조</span><span class="sxs-lookup"><span data-stu-id="4ee47-118">See also</span></span>

- [<span data-ttu-id="4ee47-119">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4ee47-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
