---
title: ICorProfilerCallback4::GetReJITParameters 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.GetReJITParameters
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::GetReJITParameters
helpviewer_keywords:
- ICorProfilerCallback4::GetReJITParameters method [.NET Framework profiling]
- GetReJITParameters method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 0e9bfe07-9f20-498c-b568-9017c8f6056c
topic_type:
- apiref
ms.openlocfilehash: d81d7275d197de1dfc99b135377459f509c2651f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439444"
---
# <a name="icorprofilercallback4getrejitparameters-method"></a><span data-ttu-id="beb12-102">ICorProfilerCallback4::GetReJITParameters 메서드</span><span class="sxs-lookup"><span data-stu-id="beb12-102">ICorProfilerCallback4::GetReJITParameters Method</span></span>
<span data-ttu-id="beb12-103">코드 프로파일러가 다시 컴파일된 새 메서드 본문에 대 한 대체 코드 생성 플래그를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="beb12-103">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="beb12-104">구문</span><span class="sxs-lookup"><span data-stu-id="beb12-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReJITParameters(     [in] ModuleID moduleId,     [in] mdMethodDef methodId,     [in] ICorProfilerFunctionControl *pFunctionControl);  
```  
  
## <a name="parameters"></a><span data-ttu-id="beb12-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="beb12-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="beb12-106">진행 CLR에서 JIT 재컴파일 매개 변수를 필요로 하는 메서드가 포함 된 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="beb12-106">[in] The module that contains the method for which the CLR needs JIT recompilation parameters.</span></span>  
  
 `methodId`  
 <span data-ttu-id="beb12-107">진행 CLR에서 JIT 재컴파일 매개 변수를 필요로 하는 메서드의 `MethodDef`입니다.</span><span class="sxs-lookup"><span data-stu-id="beb12-107">[in] The `MethodDef` of the method for which the CLR needs JIT recompilation parameters.</span></span>  
  
 `pFunctionControl`  
 <span data-ttu-id="beb12-108">진행 프로파일러가 다시 컴파일하는 메서드에 대 한 JIT 재컴파일 정보를 제공 하는 데 사용할 수 있는 [ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md) 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="beb12-108">[in] A pointer to an [ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md) interface that the profiler can use to provide JIT recompilation information for the method being recompiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="beb12-109">설명</span><span class="sxs-lookup"><span data-stu-id="beb12-109">Remarks</span></span>  
 <span data-ttu-id="beb12-110">CLR은 프로파일러가 지정 된 메서드를 다시 컴파일할 수 있도록 매개 변수를 지정할 수 있도록 `GetReJITParameters` 콜백을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="beb12-110">The CLR issues a `GetReJITParameters` callback so that the profiler can specify the parameters for recompiling a given method.</span></span> <span data-ttu-id="beb12-111">`GetReJITParameters` 콜백은 함수 마다 한 번만 실행 됩니다. 프로파일러에서 제공 하는 매개 변수는 해당 함수의 모든 인스턴스에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="beb12-111">The `GetReJITParameters` callback is issued only once per function; the parameters supplied by the profiler apply to all instances of that function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="beb12-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="beb12-112">Requirements</span></span>  
 <span data-ttu-id="beb12-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="beb12-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="beb12-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="beb12-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="beb12-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="beb12-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="beb12-116">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="beb12-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="beb12-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="beb12-117">See also</span></span>

- [<span data-ttu-id="beb12-118">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="beb12-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="beb12-119">ICorProfilerCallback4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="beb12-119">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
- [<span data-ttu-id="beb12-120">JITCompilationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="beb12-120">JITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)
- [<span data-ttu-id="beb12-121">ReJITCompilationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="beb12-121">ReJITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)
