---
title: ICorDebugILCode2::GetInstrumentedILMap 메서드
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode2.GetInstrumentedILMap
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 7a4e3085-8f95-40ef-a4be-7d6146f47ce2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1f2e481942586e1e5ea6364370ff1385db134dd3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57475686"
---
# <a name="icordebugilcode2getinstrumentedilmap-method"></a><span data-ttu-id="52352-102">ICorDebugILCode2::GetInstrumentedILMap 메서드</span><span class="sxs-lookup"><span data-stu-id="52352-102">ICorDebugILCode2::GetInstrumentedILMap Method</span></span>
<span data-ttu-id="52352-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="52352-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="52352-104">이 인스턴스에 대해 프로파일러가 계측한 IL(중간 언어) 오프셋에서 원래 메서드 IL 오프셋으로의 맵을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="52352-104">Returns a map from profiler-instrumented intermediate language (IL) offsets to original method IL offsets for this instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52352-105">구문</span><span class="sxs-lookup"><span data-stu-id="52352-105">Syntax</span></span>  
  
```cpp
HRESULT GetInstrumentedILMap(  
   [in] ULONG32 cMap,  
   [out] ULONG32 *pcMap,  
   [out, size_is(cMap), length_is(*pcMap)] COR_IL_MAP map[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52352-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="52352-106">Parameters</span></span>  
 <span data-ttu-id="52352-107">cMap</span><span class="sxs-lookup"><span data-stu-id="52352-107">cMap</span></span>  
 <span data-ttu-id="52352-108">[in] `map` 배열의 저장소 용량입니다.</span><span class="sxs-lookup"><span data-stu-id="52352-108">[in] The storage capacity of the `map` array.</span></span> <span data-ttu-id="52352-109">자세한 내용은 설명 부분을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="52352-109">See the Remarks section for more information.</span></span>  
  
 <span data-ttu-id="52352-110">pcMap</span><span class="sxs-lookup"><span data-stu-id="52352-110">pcMap</span></span>  
 <span data-ttu-id="52352-111">[out] 맵 배열에 기록 COR_IL_MAP 값의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="52352-111">[out] The number of COR_IL_MAP values written to the map array.</span></span>  
  
 <span data-ttu-id="52352-112">map</span><span class="sxs-lookup"><span data-stu-id="52352-112">map</span></span>  
 <span data-ttu-id="52352-113">[out] 원래 메서드 IL로 프로파일러가 계측 한 IL에서 매핑에 관한 정보를 제공 하는 COR_IL_MAP 값의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="52352-113">[out] An array of COR_IL_MAP values that provide information on mappings from profiler-instrumented IL to the IL of the original method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52352-114">설명</span><span class="sxs-lookup"><span data-stu-id="52352-114">Remarks</span></span>  
 <span data-ttu-id="52352-115">프로파일러를 호출 하 여 매핑을 설정 하는 경우는 [icorprofilerinfo:: Setilinstrumentedcodemap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) 메서드를 디버거 매핑을 검색 하 고 스택에 대 한 오프셋 IL을 계산할 때 내부적으로 매핑을 사용할 때이 메서드를 호출할 수 추적 및 변수 수명입니다.</span><span class="sxs-lookup"><span data-stu-id="52352-115">If the profiler sets the mapping by calling the [ICorProfilerInfo::SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) method, the debugger can call this method to retrieve the mapping and to use the mapping internally when calculating IL offsets for stack traces and variable lifetimes.</span></span>  
  
 <span data-ttu-id="52352-116">하는 경우 `cMap` 가 0 및 `pcMap` 이 아닌**null**, `pcMap` 사용 가능한 COR_IL_MAP 값의 수로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52352-116">If `cMap` is 0 and `pcMap` is non-**null**, `pcMap` is set to the number of available COR_IL_MAP values.</span></span> <span data-ttu-id="52352-117">
  `cMap\`은 값이 0이 아닌 경우 `map\` 배열의 저장소 용량을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="52352-117">If `cMap` is non-zero, it represents the storage capacity of the `map` array.</span></span> <span data-ttu-id="52352-118">메서드는 반환 될 때 `map` 의 최대값을 포함 `cMap` 항목 및 `pcMap` 에 실제로 기록 된 COR_IL_MAP 값의 수로 설정 되는 `map` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="52352-118">When the method returns, `map` contains a maximum of `cMap` items, and `pcMap` is set to the number of COR_IL_MAP values actually written to the `map` array.</span></span>  
  
 <span data-ttu-id="52352-119">IL이 계측되지 않았거나 프로파일러가 매핑을 제공하지 않은 경우 이 메서드는 `S_OK`를 반환하고 `pcMap`을 0으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="52352-119">If the IL hasn't been instrumented or the mapping wasn't provided by a profiler, this method returns `S_OK` and sets `pcMap` to 0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52352-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="52352-120">Requirements</span></span>  
 <span data-ttu-id="52352-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="52352-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52352-122">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="52352-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="52352-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52352-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52352-124">**.NET Framework 버전:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52352-124">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52352-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="52352-125">See also</span></span>
- [<span data-ttu-id="52352-126">ICorProfilerInfo::SetILInstrumentedCodeMap</span><span class="sxs-lookup"><span data-stu-id="52352-126">ICorProfilerInfo::SetILInstrumentedCodeMap</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)
- [<span data-ttu-id="52352-127">ICorDebugILCode2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="52352-127">ICorDebugILCode2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)
- [<span data-ttu-id="52352-128">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="52352-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
