---
description: '자세히 알아보기: ICorDebugFunction3:: GetActiveReJitRequestILCode 메서드'
title: ICorDebugFunction3::GetActiveReJitRequestILCode 메서드
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugFunction3.GetActiveReJitRequestILCode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 88584574-ade5-45b2-9778-489ed5c4dd7f
topic_type:
- apiref
ms.openlocfilehash: 9225c5cdf97395b7e1b11c61d653cab8d52031c6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692123"
---
# <a name="icordebugfunction3getactiverejitrequestilcode-method"></a><span data-ttu-id="c7e6a-103">ICorDebugFunction3::GetActiveReJitRequestILCode 메서드</span><span class="sxs-lookup"><span data-stu-id="c7e6a-103">ICorDebugFunction3::GetActiveReJitRequestILCode Method</span></span>

<span data-ttu-id="c7e6a-104">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="c7e6a-104">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="c7e6a-105">활성 ReJIT 요청에서 IL을 포함 하는 [ICorDebugILCode](icordebugilcode-interface.md) 에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c7e6a-105">Gets an interface pointer to an [ICorDebugILCode](icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7e6a-106">구문</span><span class="sxs-lookup"><span data-stu-id="c7e6a-106">Syntax</span></span>  
  
```cpp
HRESULT GetActiveReJitRequestILCode(  
   ICorDebugILCode **ppReJitedILCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7e6a-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c7e6a-107">Parameters</span></span>  

 `ppReJitedILCode`  
 <span data-ttu-id="c7e6a-108">활성 ReJIT 요청의 IL에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c7e6a-108">A pointer to the IL from an active ReJIT request.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7e6a-109">설명</span><span class="sxs-lookup"><span data-stu-id="c7e6a-109">Remarks</span></span>  

 <span data-ttu-id="c7e6a-110">이 `ICorDebugFunction3` 개체가 나타내는 메서드에 활성 ReJIT 요청이 있으면 `ppReJitedILCode`는 해당 IL에 대한 포인터를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c7e6a-110">If the method represented by this `ICorDebugFunction3` object has an active ReJIT request, `ppReJitedILCode` returns a pointer to its IL.</span></span> <span data-ttu-id="c7e6a-111">활성 요청이 없는 경우 (일반적인 경우) `ppReJitedILCode` 는 **null** 입니다.</span><span class="sxs-lookup"><span data-stu-id="c7e6a-111">If there is no active request, which is a common case, then `ppReJitedILCode` is **null**.</span></span>  
  
 <span data-ttu-id="c7e6a-112">ReJIT 요청은 실행이 [ICorProfilerCallback4:: GetReJITParameters](../profiling/icorprofilercallback4-getrejitparameters-method.md) 메서드 호출에서 반환 된 후에만 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7e6a-112">A ReJIT request becomes active just after execution returns from the [ICorProfilerCallback4::GetReJITParameters](../profiling/icorprofilercallback4-getrejitparameters-method.md) method call.</span></span> <span data-ttu-id="c7e6a-113">이 요청에서는 JIT가 아직 컴파일되지 않았을 수 있으며 원래 코드 버전에서 스레드가 계속 실행 중일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e6a-113">It may not yet be JIT-compiled, and threads may still be executing in the original version of the code.</span></span> <span data-ttu-id="c7e6a-114">ReJIT 요청은 프로파일러에서 [ICorProfilerInfo4:: RequestRevert](../profiling/icorprofilerinfo4-requestrevert-method.md) 메서드를 호출 하는 동안 비활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7e6a-114">A ReJIT request becomes inactive during the profiler's call to the [ICorProfilerInfo4::RequestRevert](../profiling/icorprofilerinfo4-requestrevert-method.md) method.</span></span> <span data-ttu-id="c7e6a-115">IL이 되돌려진 후에도 스레드는 JIT가 다시 컴파일된(ReJIT) 코드를 계속 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e6a-115">Even after the IL is reverted, a thread can still be executing in the JIT-recompiled (ReJIT) code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7e6a-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c7e6a-116">Requirements</span></span>  

 <span data-ttu-id="c7e6a-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7e6a-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7e6a-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c7e6a-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c7e6a-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7e6a-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7e6a-120">**.NET Framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7e6a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7e6a-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c7e6a-121">See also</span></span>

- [<span data-ttu-id="c7e6a-122">ICorDebugFunction3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c7e6a-122">ICorDebugFunction3 Interface</span></span>](icordebugfunction3-interface.md)
- [<span data-ttu-id="c7e6a-123">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c7e6a-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="c7e6a-124">ReJIT: How-To 가이드</span><span class="sxs-lookup"><span data-stu-id="c7e6a-124">ReJIT: A How-To Guide</span></span>](/archive/blogs/davbr/rejit-a-how-to-guide)
