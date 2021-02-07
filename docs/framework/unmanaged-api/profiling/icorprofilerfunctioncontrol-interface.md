---
description: '자세히 알아보기: ICorProfilerFunctionControl 인터페이스'
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
ms.openlocfilehash: 7b4ac58d2b8754108b4e10493596776987a93a49
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753317"
---
# <a name="icorprofilerfunctioncontrol-interface"></a><span data-ttu-id="a82df-103">ICorProfilerFunctionControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a82df-103">ICorProfilerFunctionControl Interface</span></span>

<span data-ttu-id="a82df-104">코드 프로파일러가 CLR(공용 언어 런타임)과 통신하여 특정 메서드를 다시 컴파일할 때 JIT 컴파일러가 코드를 생성하는 방법을 제어할 수 있도록 하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a82df-104">Provides methods that allow a code profiler to communicate with the common language runtime (CLR) to control how the JIT compiler should generate code when recompiling a specific method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a82df-105">메서드</span><span class="sxs-lookup"><span data-stu-id="a82df-105">Methods</span></span>  
  
|<span data-ttu-id="a82df-106">메서드</span><span class="sxs-lookup"><span data-stu-id="a82df-106">Method</span></span>|<span data-ttu-id="a82df-107">설명</span><span class="sxs-lookup"><span data-stu-id="a82df-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a82df-108">SetCodegenFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="a82df-108">SetCodegenFlags Method</span></span>](icorprofilerfunctioncontrol-setcodegenflags-method.md)|<span data-ttu-id="a82df-109">JIT (just in time) 컴파일 함수의 코드 생성을 제어 하기 위해 [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) 열거형에서 하나 이상의 플래그를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a82df-109">Sets one or more flags from the [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) enumeration to control code generation for a just-in-time (JIT) recompiled function.</span></span>|  
|[<span data-ttu-id="a82df-110">SetILFunctionBody 메서드</span><span class="sxs-lookup"><span data-stu-id="a82df-110">SetILFunctionBody Method</span></span>](icorprofilerfunctioncontrol-setilfunctionbody-method.md)|<span data-ttu-id="a82df-111">메서드의 공용 중간 언어(CIL) 본문을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="a82df-111">Replaces the Common Intermediate Language (CIL) body of the method.</span></span>|  
|[<span data-ttu-id="a82df-112">SetILInstrumentedCodeMap 메서드</span><span class="sxs-lookup"><span data-stu-id="a82df-112">SetILInstrumentedCodeMap Method</span></span>](icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md)|<span data-ttu-id="a82df-113">지정한 CIL(공용 중간 언어) 맵 엔트리를 사용하여 지정된 함수에 대한 코드 맵을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a82df-113">Sets a code map for the specified function by using the specified Common Intermediate Language (CIL) map entries.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a82df-114">설명</span><span class="sxs-lookup"><span data-stu-id="a82df-114">Remarks</span></span>  

 <span data-ttu-id="a82df-115">`ICorProfilerFunctionControl` 인터페이스는 다시 컴파일된 단일 함수에 대한 코드 생성을 제어하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a82df-115">The `ICorProfilerFunctionControl` interface provides methods for controlling code generation for a single recompiled function.</span></span> <span data-ttu-id="a82df-116">프로파일러는 [ICorProfilerCallback4:: GetReJITParameters](icorprofilercallback4-getrejitparameters-method.md) 콜백을 통해이 인터페이스의 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a82df-116">The profiler obtains an instance of this interface through the [ICorProfilerCallback4::GetReJITParameters](icorprofilercallback4-getrejitparameters-method.md) callback.</span></span> <span data-ttu-id="a82df-117">`ICorProfilerFunctionControl`의 각 인스턴스가 단일 함수의 모든 인스턴스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="a82df-117">Each instance of `ICorProfilerFunctionControl` controls all instances of one function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a82df-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a82df-118">Requirements</span></span>  

 <span data-ttu-id="a82df-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a82df-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a82df-120">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a82df-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a82df-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a82df-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a82df-122">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a82df-122">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a82df-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a82df-123">See also</span></span>

- [<span data-ttu-id="a82df-124">ICorProfilerInfo4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a82df-124">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="a82df-125">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a82df-125">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="a82df-126">EnumJITedFunctions2 메서드</span><span class="sxs-lookup"><span data-stu-id="a82df-126">EnumJITedFunctions2 Method</span></span>](icorprofilerinfo4-enumjitedfunctions2-method.md)
