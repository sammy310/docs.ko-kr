---
title: ICorProfilerInfo4::GetReJITIDs 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetReJITIDs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetReJITIDs
helpviewer_keywords:
- GetReJITIDs method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetReJITIDs method [.NET Framework profiling]
ms.assetid: 634ac28c-a5b7-4fc3-af84-256c24ca8177
topic_type:
- apiref
ms.openlocfilehash: 2ac645cbaaa45554568874653be016e4691bbd2f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707479"
---
# <a name="icorprofilerinfo4getrejitids-method"></a><span data-ttu-id="ead28-102">ICorProfilerInfo4::GetReJITIDs 메서드</span><span class="sxs-lookup"><span data-stu-id="ead28-102">ICorProfilerInfo4::GetReJITIDs Method</span></span>

<span data-ttu-id="ead28-103">아직 할당 된 지정 된 함수의 JIT 다시 컴파일된 모든 버전을 식별 하는 Id 배열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ead28-103">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span> <span data-ttu-id="ead28-104">여기에는 나중에 되돌린 하지만 아직 해제 되지 않은 함수의 JIT 다시 컴파일된 버전 (예: 되돌린 함수를 포함 하는 응용 프로그램 도메인이 아직 사용 중인 경우)이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ead28-104">This includes JIT-recompiled versions of functions that have been subsequently reverted but not yet freed (for example, when the application domain that contains the reverted function is still in use).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ead28-105">구문</span><span class="sxs-lookup"><span data-stu-id="ead28-105">Syntax</span></span>  
  
```cpp
HRESULT GetReJITIDs (  
     [in]  FunctionID          functionId,  
     [in]  ULONG               cReJitIds,  
     [out] ULONG *             pcReJitIds,  
     [out, size_is(cReJitIds), length_is(*pcReJitIds)]   ReJITID        reJitIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ead28-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ead28-106">Parameters</span></span>  

 `functionId`  
 <span data-ttu-id="ead28-107">진행 `FunctionID` 버전을 열거할 함수 인스턴스의입니다.</span><span class="sxs-lookup"><span data-stu-id="ead28-107">[in] The `FunctionID` of the function instance for which to enumerate versions.</span></span>  
  
 `cReJitIds`  
 <span data-ttu-id="ead28-108">진행 배열에 할당 된 JIT 다시 컴파일된 Id의 수입니다 `reJitIds` .</span><span class="sxs-lookup"><span data-stu-id="ead28-108">[in] The number of JIT-recompiled IDs allocated in the `reJitIds` array.</span></span>  
  
 `pcReJitIds`  
 <span data-ttu-id="ead28-109">제한이 JIT 다시 컴파일된 Id의 실제 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ead28-109">[out] The actual number of JIT-recompiled IDs.</span></span>  
  
 `reJitIds`  
 <span data-ttu-id="ead28-110">제한이 지정 된 함수의 JIT 다시 컴파일된 Id를 포함 하는 호출자가 할당 한 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="ead28-110">[out] A caller-allocated array that will contain the JIT-recompiled IDs for the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ead28-111">설명</span><span class="sxs-lookup"><span data-stu-id="ead28-111">Remarks</span></span>  

 <span data-ttu-id="ead28-112">`GetReJITIDs` 지정 된 함수 인스턴스에 대 한 활성 JIT 다시 컴파일된 Id를 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="ead28-112">`GetReJITIDs` enumerates the active JIT-recompiled IDs for a given function instance.</span></span> <span data-ttu-id="ead28-113">`ICorProfilerInfo`호출자가 할당 한 버퍼를 허용 하는 다른 함수와 동일한 사용 패턴을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="ead28-113">It follows the same usage pattern as other `ICorProfilerInfo` functions that accept caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ead28-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ead28-114">Requirements</span></span>  

 <span data-ttu-id="ead28-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ead28-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ead28-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ead28-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ead28-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ead28-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ead28-118">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ead28-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ead28-119">참조</span><span class="sxs-lookup"><span data-stu-id="ead28-119">See also</span></span>

- [<span data-ttu-id="ead28-120">ICorProfilerInfo4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ead28-120">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="ead28-121">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ead28-121">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="ead28-122">프로파일링</span><span class="sxs-lookup"><span data-stu-id="ead28-122">Profiling</span></span>](index.md)
