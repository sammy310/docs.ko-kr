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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9d2d48e5fb070ec0334de579d2e28146177a87b1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121617"
---
# <a name="icorprofilerinfo4getrejitids-method"></a><span data-ttu-id="a7ced-102">ICorProfilerInfo4::GetReJITIDs 메서드</span><span class="sxs-lookup"><span data-stu-id="a7ced-102">ICorProfilerInfo4::GetReJITIDs Method</span></span>
<span data-ttu-id="a7ced-103">모든 JIT 다시 컴파일된 버전의 지정 된 함수가 여전히 할당 되는 식별 하는 Id의 배열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ced-103">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span> <span data-ttu-id="a7ced-104">이 이후에 되돌릴 되었지만 아직 서비스 되지 않음 (예를 들어 되돌려 진된 함수를 포함 하는 응용 프로그램 도메인 사용 중인 경우 계속)를 해제 하는 함수의 JIT 다시 컴파일된 버전을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ced-104">This includes JIT-recompiled versions of functions that have been subsequently reverted but not yet freed (for example, when the application domain that contains the reverted function is still in use).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7ced-105">구문</span><span class="sxs-lookup"><span data-stu-id="a7ced-105">Syntax</span></span>  
  
```  
HRESULT GetReJITIDs (  
     [in]  FunctionID          functionId,  
     [in]  ULONG               cReJitIds,  
     [out] ULONG *             pcReJitIds,  
     [out, size_is(cReJitIds), length_is(*pcReJitIds)]   ReJITID        reJitIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7ced-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a7ced-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="a7ced-107">[in] `FunctionID` 열거할 버전에 대 한 함수 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="a7ced-107">[in] The `FunctionID` of the function instance for which to enumerate versions.</span></span>  
  
 `cReJitIds`  
 <span data-ttu-id="a7ced-108">[in] JIT 다시 컴파일된 Id에 할당 된 수의 `reJitIds` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="a7ced-108">[in] The number of JIT-recompiled IDs allocated in the `reJitIds` array.</span></span>  
  
 `pcReJitIds`  
 <span data-ttu-id="a7ced-109">[out] JIT 다시 컴파일된 Id의 실제 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a7ced-109">[out] The actual number of JIT-recompiled IDs.</span></span>  
  
 `reJitIds`  
 <span data-ttu-id="a7ced-110">[out] 지정 된 함수의 JIT 다시 컴파일된 Id를 포함 하는 호출자에 게 할당 된 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="a7ced-110">[out] A caller-allocated array that will contain the JIT-recompiled IDs for the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7ced-111">설명</span><span class="sxs-lookup"><span data-stu-id="a7ced-111">Remarks</span></span>  
 `GetReJITIDs` <span data-ttu-id="a7ced-112">지정 된 함수 인스턴스에 대 한 활성 JIT 다시 컴파일된 Id를 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ced-112">enumerates the active JIT-recompiled IDs for a given function instance.</span></span> <span data-ttu-id="a7ced-113">다른 것과 동일한 사용 패턴을 따릅니다 `ICorProfilerInfo` 호출자 할당 버퍼를 허용 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="a7ced-113">It follows the same usage pattern as other `ICorProfilerInfo` functions that accept caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7ced-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a7ced-114">Requirements</span></span>  
 <span data-ttu-id="a7ced-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a7ced-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7ced-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a7ced-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a7ced-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7ced-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="a7ced-118">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="a7ced-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a7ced-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="a7ced-119">See also</span></span>

- [<span data-ttu-id="a7ced-120">ICorProfilerInfo4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a7ced-120">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="a7ced-121">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a7ced-121">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="a7ced-122">프로파일링</span><span class="sxs-lookup"><span data-stu-id="a7ced-122">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
