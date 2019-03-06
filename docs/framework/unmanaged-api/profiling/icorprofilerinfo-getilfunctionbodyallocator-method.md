---
title: ICorProfilerInfo::GetILFunctionBodyAllocator 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILFunctionBodyAllocator
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILFunctionBodyAllocator
helpviewer_keywords:
- GetILFunctionBodyAllocator method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBodyAllocator method [.NET Framework profiling]
ms.assetid: 5da1bf3d-dddf-4892-b266-578ee54d570b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 432ebff36f3b4ee0362e01fc5ecd1bfdb35bc493
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57493013"
---
# <a name="icorprofilerinfogetilfunctionbodyallocator-method"></a><span data-ttu-id="c3d09-102">ICorProfilerInfo::GetILFunctionBodyAllocator 메서드</span><span class="sxs-lookup"><span data-stu-id="c3d09-102">ICorProfilerInfo::GetILFunctionBodyAllocator Method</span></span>
<span data-ttu-id="c3d09-103">Microsoft MSIL (intermediate language) 코드에서 메서드 본문을 바꾸는 데 사용 하는 메모리를 할당 하기 위한 메서드를 제공 하는 인터페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c3d09-103">Gets an interface that provides a method to allocate memory to be used for swapping out the body of a method in Microsoft intermediate language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3d09-104">구문</span><span class="sxs-lookup"><span data-stu-id="c3d09-104">Syntax</span></span>  
  
```  
HRESULT GetILFunctionBodyAllocator(  
    [in]  ModuleID      moduleId,  
    [out] IMethodMalloc **ppMalloc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3d09-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c3d09-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="c3d09-106">[in] 메서드가 상주 하는 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c3d09-106">[in] The ID of the module in which the method resides.</span></span>  
  
 `ppMalloc`  
 <span data-ttu-id="c3d09-107">[out] 에 대 한 포인터를 [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) 메모리를 할당 하는 메서드를 제공 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="c3d09-107">[out] A pointer to an [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) interface that provides a method to allocate the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3d09-108">설명</span><span class="sxs-lookup"><span data-stu-id="c3d09-108">Remarks</span></span>  
 <span data-ttu-id="c3d09-109">MSIL 코드에서 메서드 본문을 4GB 모듈만 따르는지 즉 로드 된 모듈을 기준으로 상대 가상 주소 (RVA)로 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3d09-109">A method body in MSIL code must be located as a relative virtual address (RVA), relative to the loaded module, which means that it follows the module within 4 GB.</span></span> <span data-ttu-id="c3d09-110">메서드의 본문도 스왑할를 도구용 쉽게는 `GetILFunctionBodyAllocator` 메서드를 사용 하면 메모리 범위 내에서 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3d09-110">To make it easier for a tool to swap out the body of a method, the `GetILFunctionBodyAllocator` method ensures that memory is allocated within that range.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3d09-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c3d09-111">Requirements</span></span>  
 <span data-ttu-id="c3d09-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c3d09-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3d09-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c3d09-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c3d09-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3d09-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c3d09-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3d09-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3d09-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="c3d09-116">See also</span></span>
- [<span data-ttu-id="c3d09-117">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c3d09-117">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
