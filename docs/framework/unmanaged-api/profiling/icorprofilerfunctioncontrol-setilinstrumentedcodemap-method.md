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
ms.openlocfilehash: 738c98a0a37983faa71ea6e5eeaabb20639f604a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503143"
---
# <a name="icorprofilerfunctioncontrolsetilinstrumentedcodemap-method"></a><span data-ttu-id="108d7-102">ICorProfilerFunctionControl::SetILInstrumentedCodeMap 메서드</span><span class="sxs-lookup"><span data-stu-id="108d7-102">ICorProfilerFunctionControl::SetILInstrumentedCodeMap Method</span></span>
<span data-ttu-id="108d7-103">지정한 CIL(공용 중간 언어) 맵 엔트리를 사용하여 지정된 함수에 대한 코드 맵을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="108d7-103">Sets a code map for the specified function by using the specified Common Intermediate Language (CIL) map entries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="108d7-104">구문</span><span class="sxs-lookup"><span data-stu-id="108d7-104">Syntax</span></span>  
  
```cpp  
HRESULT SetILInstrumentedCodeMap(  
    [in]   ULONG      cILMapEntries,  
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="108d7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="108d7-105">Parameters</span></span>  
 `cILMapEntries`  
 <span data-ttu-id="108d7-106">[in] 맵의 엔트리 수입니다.</span><span class="sxs-lookup"><span data-stu-id="108d7-106">[in] The number of entries in the map.</span></span>  
  
 `rgILMapEntries`  
 <span data-ttu-id="108d7-107">[in] 호출자가 할당한 COR_IL_MAP 엔트리 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="108d7-107">[in] The caller-allocated array of COR_IL_MAP  entries.</span></span> <span data-ttu-id="108d7-108">이러한 항목의 해석은 [ICorProfilerInfo:: SetILInstrumentedCodeMap](icorprofilerinfo-setilinstrumentedcodemap-method.md) 메서드와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="108d7-108">The interpretation of these entries is the same as for the [ICorProfilerInfo::SetILInstrumentedCodeMap](icorprofilerinfo-setilinstrumentedcodemap-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="108d7-109">설명</span><span class="sxs-lookup"><span data-stu-id="108d7-109">Remarks</span></span>  
 <span data-ttu-id="108d7-110">이 메서드를 호출 하 여 매핑을 설정 하면 디버거가 [ICorDebugILCode2:: GetInstrumentedILMap](../debugging/icordebugilcode2-getinstrumentedilmap-method.md)를 호출 하 여 매핑을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="108d7-110">Setting the mapping by calling this method allows the debugger to retrieve the mapping by calling [ICorDebugILCode2::GetInstrumentedILMap](../debugging/icordebugilcode2-getinstrumentedilmap-method.md).</span></span> <span data-ttu-id="108d7-111">또한 스택 추적 및 변수 수명에 대한 IL 오프셋을 계산할 때 디버거가 내부적으로 매핑을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="108d7-111">It also allows the debugger to use the mapping internally when calculating IL offsets for stack traces and variable lifetimes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="108d7-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="108d7-112">Requirements</span></span>  
 <span data-ttu-id="108d7-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="108d7-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="108d7-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="108d7-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="108d7-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="108d7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="108d7-116">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="108d7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="108d7-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="108d7-117">See also</span></span>

- [<span data-ttu-id="108d7-118">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="108d7-118">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
