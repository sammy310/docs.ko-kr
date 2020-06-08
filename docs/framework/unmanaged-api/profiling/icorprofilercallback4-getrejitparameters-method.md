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
ms.openlocfilehash: 527e48d02d5267d6ae41214686c2e8c997d85dca
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499547"
---
# <a name="icorprofilercallback4getrejitparameters-method"></a><span data-ttu-id="4fc91-102">ICorProfilerCallback4::GetReJITParameters 메서드</span><span class="sxs-lookup"><span data-stu-id="4fc91-102">ICorProfilerCallback4::GetReJITParameters Method</span></span>
<span data-ttu-id="4fc91-103">코드 프로파일러가 다시 컴파일된 새 메서드 본문에 대 한 대체 코드 생성 플래그를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fc91-103">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fc91-104">구문</span><span class="sxs-lookup"><span data-stu-id="4fc91-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReJITParameters(     [in] ModuleID moduleId,     [in] mdMethodDef methodId,     [in] ICorProfilerFunctionControl *pFunctionControl);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4fc91-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4fc91-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="4fc91-106">진행 CLR에서 JIT 재컴파일 매개 변수를 필요로 하는 메서드가 포함 된 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="4fc91-106">[in] The module that contains the method for which the CLR needs JIT recompilation parameters.</span></span>  
  
 `methodId`  
 <span data-ttu-id="4fc91-107">진행 `MethodDef`CLR에서 JIT 재컴파일 매개 변수를 필요로 하는 메서드의입니다.</span><span class="sxs-lookup"><span data-stu-id="4fc91-107">[in] The `MethodDef` of the method for which the CLR needs JIT recompilation parameters.</span></span>  
  
 `pFunctionControl`  
 <span data-ttu-id="4fc91-108">진행 프로파일러가 다시 컴파일하는 메서드에 대 한 JIT 재컴파일 정보를 제공 하는 데 사용할 수 있는 [ICorProfilerFunctionControl](icorprofilerfunctioncontrol-interface.md) 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4fc91-108">[in] A pointer to an [ICorProfilerFunctionControl](icorprofilerfunctioncontrol-interface.md) interface that the profiler can use to provide JIT recompilation information for the method being recompiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4fc91-109">설명</span><span class="sxs-lookup"><span data-stu-id="4fc91-109">Remarks</span></span>  
 <span data-ttu-id="4fc91-110">`GetReJITParameters`프로파일러가 지정 된 메서드를 다시 컴파일하는 매개 변수를 지정할 수 있도록 CLR은 콜백을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc91-110">The CLR issues a `GetReJITParameters` callback so that the profiler can specify the parameters for recompiling a given method.</span></span> <span data-ttu-id="4fc91-111">`GetReJITParameters`콜백은 함수 마다 한 번만 실행 됩니다. 프로파일러에서 제공 하는 매개 변수는 해당 함수의 모든 인스턴스에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fc91-111">The `GetReJITParameters` callback is issued only once per function; the parameters supplied by the profiler apply to all instances of that function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4fc91-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4fc91-112">Requirements</span></span>  
 <span data-ttu-id="4fc91-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4fc91-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4fc91-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4fc91-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4fc91-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4fc91-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4fc91-116">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4fc91-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fc91-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4fc91-117">See also</span></span>

- [<span data-ttu-id="4fc91-118">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4fc91-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="4fc91-119">ICorProfilerCallback4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4fc91-119">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
- [<span data-ttu-id="4fc91-120">JITCompilationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="4fc91-120">JITCompilationStarted Method</span></span>](icorprofilercallback-jitcompilationstarted-method.md)
- [<span data-ttu-id="4fc91-121">ReJITCompilationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="4fc91-121">ReJITCompilationStarted Method</span></span>](icorprofilercallback4-rejitcompilationstarted-method.md)
