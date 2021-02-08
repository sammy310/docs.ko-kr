---
description: '자세히 알아보기: ICorProfilerFunctionControl:: SetCodegenFlags 메서드'
title: ICorProfilerFunctionControl::SetCodegenFlags 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl.SetCodegenFlags
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl::SetCodegenFlags
helpviewer_keywords:
- ICorProfilerFunctionControl::SetCodegenFlags method [.NET Framework profiling]
- SetCodegenFlags method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: a2d5daa5-b990-4ae5-bf2a-c0862fe58bd7
topic_type:
- apiref
ms.openlocfilehash: 61fa8be0993a06a3b2d352af408ac47b7b30e385
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781625"
---
# <a name="icorprofilerfunctioncontrolsetcodegenflags-method"></a><span data-ttu-id="d8472-103">ICorProfilerFunctionControl::SetCodegenFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="d8472-103">ICorProfilerFunctionControl::SetCodegenFlags Method</span></span>

<span data-ttu-id="d8472-104">JIT (just in time) 컴파일 함수의 코드 생성을 제어 하기 위해 [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) 열거형에서 하나 이상의 플래그를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8472-104">Sets one or more flags from the [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) enumeration to control code generation for a just-in-time (JIT) recompiled function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8472-105">구문</span><span class="sxs-lookup"><span data-stu-id="d8472-105">Syntax</span></span>  
  
```cpp  
HRESULT SetCodegenFlags(  
    [in] DWORD flags);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8472-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d8472-106">Parameters</span></span>  

 `flags`  
 <span data-ttu-id="d8472-107">진행 [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) 열거형의 하나 이상의 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="d8472-107">[in] One or more flags from the [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8472-108">설명</span><span class="sxs-lookup"><span data-stu-id="d8472-108">Remarks</span></span>  

 <span data-ttu-id="d8472-109">프로파일러는 [ICorProfilerCallback4:: GetReJITParameters](icorprofilercallback4-getrejitparameters-method.md) 콜백을 통해이 인터페이스의 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d8472-109">The profiler obtains an instance of this interface through the [ICorProfilerCallback4::GetReJITParameters](icorprofilercallback4-getrejitparameters-method.md) callback.</span></span> <span data-ttu-id="d8472-110">`SetCodegenFlags` 프로파일러가 다시 컴파일된 함수에 대 한 코드 생성을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8472-110">`SetCodegenFlags` allows the profiler to control the code generation for the recompiled function.</span></span> <span data-ttu-id="d8472-111">다른 모든 JIT 재컴파일 매개 변수와 마찬가지로 코드 생성 플래그는 함수의 모든 인스턴스에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8472-111">As with all other JIT recompilation parameters, the code generation flags apply to all instances of the function.</span></span>  
  
 <span data-ttu-id="d8472-112">JIT 컴파일러는 함수를 컴파일할 때 다른 원본에서 지정 된 다른 플래그와 함께 이러한 컴파일 플래그를 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8472-112">The JIT compiler considers these compilation flags, along with other flags specified by other sources, when compiling a function.</span></span>  <span data-ttu-id="d8472-113">다른 원본에는 [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) 메서드 (값 `COR_PRF_DISABLE_INLINING` 및 `COR_PRF_DISABLE_OPTIMIZATIONS` )와 프로파일러의 [ICorProfilerCallback:: JITInlining](icorprofilercallback-jitinlining-method.md) callback을 사용 하 여 시작 시 프로파일러에서 설정한 디버거, 전역 플래그가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8472-113">The other sources include the debugger, global flags set by the profiler on startup by using the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method (with the values `COR_PRF_DISABLE_INLINING` and `COR_PRF_DISABLE_OPTIMIZATIONS`), and the profiler’s [ICorProfilerCallback::JITInlining](icorprofilercallback-jitinlining-method.md) callback.</span></span>  <span data-ttu-id="d8472-114">JIT 컴파일러는 최소한의 최적화를 요청 하는 소스에 우선 순위를 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8472-114">The JIT compiler gives precedence to a source that requests the least amount of optimizing.</span></span>  <span data-ttu-id="d8472-115">예를 들어 프로파일러가 `COR_PRF_DISABLE_INLINING` 시작 시를 지정 하지만 `COR_PRF_CODEGEN_DISABLE_INLINING` [ICorProfilerFunctionControl:: SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) 콜백에서를 지정 하지 않는 경우에도 인라이닝을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d8472-115">For example, if the profiler specifies `COR_PRF_DISABLE_INLINING` on startup, but does not specify `COR_PRF_CODEGEN_DISABLE_INLINING` in the [ICorProfilerFunctionControl::SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) callback, inlining is still disabled.</span></span>  <span data-ttu-id="d8472-116">마찬가지로 프로파일러가에서을 지정 하지 않고 `COR_PRF_CODEGEN_DISABLE_INLINING` `SetCodegenFlags` [ICorProfilerCallback:: JITInlining](icorprofilercallback-jitinlining-method.md) 콜백을 사용 하 여 인라이닝을 사용 하지 않도록 설정 하면 인라이닝을 사용 하지 않도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8472-116">Similarly, if the profiler does not specify `COR_PRF_CODEGEN_DISABLE_INLINING` in `SetCodegenFlags`, but then disables inlining by using the [ICorProfilerCallback::JITInlining](icorprofilercallback-jitinlining-method.md) callback, inlining is disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8472-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d8472-117">Requirements</span></span>  

 <span data-ttu-id="d8472-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8472-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8472-119">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d8472-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d8472-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8472-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8472-121">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8472-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8472-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d8472-122">See also</span></span>

- [<span data-ttu-id="d8472-123">ICorProfilerFunctionControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d8472-123">ICorProfilerFunctionControl Interface</span></span>](icorprofilerfunctioncontrol-interface.md)
