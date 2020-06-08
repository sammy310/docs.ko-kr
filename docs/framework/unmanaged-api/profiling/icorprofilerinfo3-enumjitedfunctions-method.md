---
title: ICorProfilerInfo3::EnumJITedFunctions 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.EnumJITedFunctions Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::EnumJITedFunctions
helpviewer_keywords:
- ICorProfilerInfo3::EnumJITedFunctions method [.NET Framework profiling]
- EnumJITedFunctions method [.NET Framework profiling]
ms.assetid: e2847a36-f460-45e2-9b6c-b33b008f40d9
topic_type:
- apiref
ms.openlocfilehash: 3ebf4a7706b3d3495e4a617b4f86a50281115436
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496557"
---
# <a name="icorprofilerinfo3enumjitedfunctions-method"></a><span data-ttu-id="64a2b-102">ICorProfilerInfo3::EnumJITedFunctions 메서드</span><span class="sxs-lookup"><span data-stu-id="64a2b-102">ICorProfilerInfo3::EnumJITedFunctions Method</span></span>
<span data-ttu-id="64a2b-103">이전에 JIT 컴파일된 모든 함수에 대 한 열거자를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="64a2b-103">Returns an enumerator for all functions that were previously JIT-compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64a2b-104">구문</span><span class="sxs-lookup"><span data-stu-id="64a2b-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64a2b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="64a2b-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="64a2b-106">제한이 [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="64a2b-106">[out] A pointer to the [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64a2b-107">설명</span><span class="sxs-lookup"><span data-stu-id="64a2b-107">Remarks</span></span>  
 <span data-ttu-id="64a2b-108">이 메서드 `JITCompilation` 는 [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) 메서드와 같은 콜백과 겹칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64a2b-108">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="64a2b-109">이 메서드에서 반환 되는 열거자에는 Ngen.exe를 사용 하 여 생성 된 네이티브 이미지에서 로드 된 함수가 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="64a2b-109">The enumerator returned by this method does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="64a2b-110">반환 된 열거형에는 필드 값에 대해 "0"만 포함 됩니다 `COR_PRF_FUNCTION::reJitId` .</span><span class="sxs-lookup"><span data-stu-id="64a2b-110">The returned enumeration includes only "0" for the value of the `COR_PRF_FUNCTION::reJitId` field.</span></span>  <span data-ttu-id="64a2b-111">유효한 값이 필요한 경우 `COR_PRF_FUNCTION::reJitId` [ICorProfilerInfo4:: EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="64a2b-111">If you require valid `COR_PRF_FUNCTION::reJitId` values, use the [ICorProfilerInfo4::EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64a2b-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="64a2b-112">Requirements</span></span>  
 <span data-ttu-id="64a2b-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="64a2b-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64a2b-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="64a2b-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="64a2b-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="64a2b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="64a2b-116">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64a2b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64a2b-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="64a2b-117">See also</span></span>

- [<span data-ttu-id="64a2b-118">ICorProfilerInfo3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="64a2b-118">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="64a2b-119">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="64a2b-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="64a2b-120">프로파일링</span><span class="sxs-lookup"><span data-stu-id="64a2b-120">Profiling</span></span>](index.md)
