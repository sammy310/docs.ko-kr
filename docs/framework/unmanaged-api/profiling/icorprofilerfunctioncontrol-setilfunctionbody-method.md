---
title: ICorProfilerFunctionControl::SetILFunctionBody 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl.SetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerFunctionControl::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: 2c33f0f7-75b2-4c19-b2c7-c94b54997576
topic_type:
- apiref
ms.openlocfilehash: f6e2cfe47bdd212e39549544b06bf5b11033a956
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74429891"
---
# <a name="icorprofilerfunctioncontrolsetilfunctionbody-method"></a><span data-ttu-id="6c601-102">ICorProfilerFunctionControl::SetILFunctionBody 메서드</span><span class="sxs-lookup"><span data-stu-id="6c601-102">ICorProfilerFunctionControl::SetILFunctionBody Method</span></span>
<span data-ttu-id="6c601-103">메서드의 공용 중간 언어(CIL) 본문을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="6c601-103">Replaces the Common Intermediate Language (CIL) body of the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c601-104">구문</span><span class="sxs-lookup"><span data-stu-id="6c601-104">Syntax</span></span>  
  
```cpp  
HRESULT SetILFunctionBody(  
    [in]  ULONG   cbNewILMethodHeader,  
    [in, size_is(cbNewILMethodHeader)] LPCBYTE pbNewILMethodHeader);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c601-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6c601-105">Parameters</span></span>  
 `cbNewILMethodHeader`  
 <span data-ttu-id="6c601-106">[in] 헤더와 본문 다음에 오는 모든 구조를 포함한 새 CIL의 총 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="6c601-106">[in] The total size of the new CIL, including the header and any structures that come after the body.</span></span>  
  
 `pbNewILMethodHeader`  
 <span data-ttu-id="6c601-107">[in] 새 CIL 헤더에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6c601-107">[in] A pointer to the new CIL header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6c601-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="6c601-108">Return Value</span></span>  
 <span data-ttu-id="6c601-109">이 메서드는 다음과 같은 특정 HRESULT를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6c601-109">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="6c601-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6c601-110">HRESULT</span></span>|<span data-ttu-id="6c601-111">설명</span><span class="sxs-lookup"><span data-stu-id="6c601-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6c601-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="6c601-112">S_OK</span></span>|<span data-ttu-id="6c601-113">바꾸기에 성공했습니다.</span><span class="sxs-lookup"><span data-stu-id="6c601-113">The replacement was successful.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c601-114">주의</span><span class="sxs-lookup"><span data-stu-id="6c601-114">Remarks</span></span>  
 <span data-ttu-id="6c601-115">Unlike the [ICorProfilerInfo::SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) method, the `SetILFunctionBody` method manages the memory required for the new CIL body.</span><span class="sxs-lookup"><span data-stu-id="6c601-115">Unlike the [ICorProfilerInfo::SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) method, the `SetILFunctionBody` method manages the memory required for the new CIL body.</span></span> <span data-ttu-id="6c601-116">This means that the CIL body provided by the profiler does not have to be allocated by using the [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) interface or allocated within a particular range.</span><span class="sxs-lookup"><span data-stu-id="6c601-116">This means that the CIL body provided by the profiler does not have to be allocated by using the [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) interface or allocated within a particular range.</span></span> <span data-ttu-id="6c601-117">어떤 힙에든 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c601-117">It can be allocated on any heap.</span></span> <span data-ttu-id="6c601-118">The profiler can free the memory used for its CIL body after `SetILFunctionBody` returns.</span><span class="sxs-lookup"><span data-stu-id="6c601-118">The profiler can free the memory used for its CIL body after `SetILFunctionBody` returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c601-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6c601-119">Requirements</span></span>  
 <span data-ttu-id="6c601-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6c601-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c601-121">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6c601-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6c601-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6c601-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6c601-123">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c601-123">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c601-124">참조</span><span class="sxs-lookup"><span data-stu-id="6c601-124">See also</span></span>

- [<span data-ttu-id="6c601-125">ICorProfilerFunctionControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6c601-125">ICorProfilerFunctionControl Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)
