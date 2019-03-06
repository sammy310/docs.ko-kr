---
title: ICorProfilerFunctionControl::SetILInstrumentedCodeMap 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl.SetILInstrumentedCodeMap
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl::SetILInstrumentedCodeMap
helpviewer_keywords:
- ICorProfilerFunctionControl::SetILInstrumentedCodeMap method [.NET Framework profiling]
- SetIILInstrumentedCodeMap method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: ecf56646-7e5f-46c4-8340-f3a04e88920f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 328702b48de8f3c471783743fb84a271f608a97a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57477129"
---
# <a name="icorprofilerfunctioncontrolsetilinstrumentedcodemap-method"></a><span data-ttu-id="8a8e5-102">ICorProfilerFunctionControl::SetILInstrumentedCodeMap 메서드</span><span class="sxs-lookup"><span data-stu-id="8a8e5-102">ICorProfilerFunctionControl::SetILInstrumentedCodeMap Method</span></span>
<span data-ttu-id="8a8e5-103">지정한 CIL(공용 중간 언어) 맵 엔트리를 사용하여 지정된 함수에 대한 코드 맵을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8a8e5-103">Sets a code map for the specified function by using the specified Common Intermediate Language (CIL) map entries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a8e5-104">구문</span><span class="sxs-lookup"><span data-stu-id="8a8e5-104">Syntax</span></span>  
  
```  
HRESULT SetILInstrumentedCodeMap(  
    [in]   ULONG      cILMapEntries,  
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a8e5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8a8e5-105">Parameters</span></span>  
 `cILMapEntries`  
 <span data-ttu-id="8a8e5-106">[in] 맵의 엔트리 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8a8e5-106">[in] The number of entries in the map.</span></span>  
  
 `rgILMapEntries`  
 <span data-ttu-id="8a8e5-107">[in] COR_IL_MAP 항목 배열을 호출자가 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a8e5-107">[in] The caller-allocated array of COR_IL_MAP  entries.</span></span> <span data-ttu-id="8a8e5-108">이러한 항목의 해석의 경우와 동일 합니다 [icorprofilerinfo:: Setilinstrumentedcodemap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="8a8e5-108">The interpretation of these entries is the same as for the [ICorProfilerInfo::SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a8e5-109">설명</span><span class="sxs-lookup"><span data-stu-id="8a8e5-109">Remarks</span></span>  
 <span data-ttu-id="8a8e5-110">이 메서드를 호출 하 여 매핑을 설정 디버거를 호출 하 여 매핑을 검색할 수 있습니다. [ICorDebugILCode2::GetInstrumentedILMap](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8a8e5-110">Setting the mapping by calling this method allows the debugger to retrieve the mapping by calling [ICorDebugILCode2::GetInstrumentedILMap](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md).</span></span> <span data-ttu-id="8a8e5-111">또한 스택 추적 및 변수 수명에 대한 IL 오프셋을 계산할 때 디버거가 내부적으로 매핑을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a8e5-111">It also allows the debugger to use the mapping internally when calculating IL offsets for stack traces and variable lifetimes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a8e5-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8a8e5-112">Requirements</span></span>  
 <span data-ttu-id="8a8e5-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8a8e5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a8e5-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8a8e5-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8a8e5-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a8e5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a8e5-116">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a8e5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a8e5-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="8a8e5-117">See also</span></span>
- [<span data-ttu-id="8a8e5-118">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8a8e5-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
