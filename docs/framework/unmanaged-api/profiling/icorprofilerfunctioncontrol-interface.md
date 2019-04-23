---
title: ICorProfilerFunctionControl 인터페이스
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl
helpviewer_keywords:
- ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: 4e3d3141-4662-4166-8f05-bc857c1b4216
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 721ee27522b316a561e2f64a322c225cb85a44c8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59211441"
---
# <a name="icorprofilerfunctioncontrol-interface"></a><span data-ttu-id="ce57b-102">ICorProfilerFunctionControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ce57b-102">ICorProfilerFunctionControl Interface</span></span>
<span data-ttu-id="ce57b-103">코드 프로파일러가 CLR(공용 언어 런타임)과 통신하여 특정 메서드를 다시 컴파일할 때 JIT 컴파일러가 코드를 생성하는 방법을 제어할 수 있도록 하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ce57b-103">Provides methods that allow a code profiler to communicate with the common language runtime (CLR) to control how the JIT compiler should generate code when recompiling a specific method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ce57b-104">메서드</span><span class="sxs-lookup"><span data-stu-id="ce57b-104">Methods</span></span>  
  
|<span data-ttu-id="ce57b-105">메서드</span><span class="sxs-lookup"><span data-stu-id="ce57b-105">Method</span></span>|<span data-ttu-id="ce57b-106">설명</span><span class="sxs-lookup"><span data-stu-id="ce57b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ce57b-107">SetCodegenFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="ce57b-107">SetCodegenFlags Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md)|<span data-ttu-id="ce57b-108">하나 이상의 플래그를 설정 합니다 [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) 다시 컴파일된 함수는-just-in-time (JIT)에 대 한 코드 생성을 제어 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="ce57b-108">Sets one or more flags from the [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeration to control code generation for a just-in-time (JIT) recompiled function.</span></span>|  
|[<span data-ttu-id="ce57b-109">SetILFunctionBody 메서드</span><span class="sxs-lookup"><span data-stu-id="ce57b-109">SetILFunctionBody Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilfunctionbody-method.md)|<span data-ttu-id="ce57b-110">메서드의 공용 중간 언어(CIL) 본문을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="ce57b-110">Replaces the Common Intermediate Language (CIL) body of the method.</span></span>|  
|[<span data-ttu-id="ce57b-111">SetILInstrumentedCodeMap 메서드</span><span class="sxs-lookup"><span data-stu-id="ce57b-111">SetILInstrumentedCodeMap Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md)|<span data-ttu-id="ce57b-112">지정한 CIL(공용 중간 언어) 맵 엔트리를 사용하여 지정된 함수에 대한 코드 맵을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ce57b-112">Sets a code map for the specified function by using the specified Common Intermediate Language (CIL) map entries.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce57b-113">설명</span><span class="sxs-lookup"><span data-stu-id="ce57b-113">Remarks</span></span>  
 <span data-ttu-id="ce57b-114">`ICorProfilerFunctionControl` 인터페이스는 다시 컴파일된 단일 함수에 대한 코드 생성을 제어하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ce57b-114">The `ICorProfilerFunctionControl` interface provides methods for controlling code generation for a single recompiled function.</span></span> <span data-ttu-id="ce57b-115">프로파일러를 통해이 인터페이스의 인스턴스를 가져오고 합니다 [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce57b-115">The profiler obtains an instance of this interface through the [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) callback.</span></span> <span data-ttu-id="ce57b-116">`ICorProfilerFunctionControl`의 각 인스턴스가 단일 함수의 모든 인스턴스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="ce57b-116">Each instance of `ICorProfilerFunctionControl` controls all instances of one function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce57b-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ce57b-117">Requirements</span></span>  
 <span data-ttu-id="ce57b-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ce57b-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce57b-119">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ce57b-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ce57b-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce57b-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce57b-121">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce57b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce57b-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="ce57b-122">See also</span></span>

- [<span data-ttu-id="ce57b-123">ICorProfilerInfo4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ce57b-123">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="ce57b-124">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ce57b-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="ce57b-125">EnumJITedFunctions2 메서드</span><span class="sxs-lookup"><span data-stu-id="ce57b-125">EnumJITedFunctions2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md)
