---
title: ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.SetEnterLeaveFunctionHooks2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::SetEnterLeaveFunctionHooks2
helpviewer_keywords:
- ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 method [.NET Framework profiling]
- SetEnterLeaveFunctionHooks2 method [.NET Framework profiling]
ms.assetid: 3c26b3e7-f72b-48a5-bf8c-edc122523a4b
topic_type:
- apiref
ms.openlocfilehash: 78489aae840ff17e68b10bd7593fb7be4dae1af7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496739"
---
# <a name="icorprofilerinfo2setenterleavefunctionhooks2-method"></a><span data-ttu-id="ac9fe-102">ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 메서드</span><span class="sxs-lookup"><span data-stu-id="ac9fe-102">ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 Method</span></span>
<span data-ttu-id="ac9fe-103">관리 되는 함수의 "enter", "leave" 및 "tailcall" 후크에 대 한 업데이트 된 버전에 대해 호출 될 프로파일러 구현 함수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac9fe-103">Specifies profiler-implemented functions to be called on the updated versions of the "enter", "leave", and "tailcall" hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac9fe-104">구문</span><span class="sxs-lookup"><span data-stu-id="ac9fe-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks2(  
    [in] FunctionEnter2    *pFuncEnter,  
    [in] FunctionLeave2    *pFuncLeave,  
    [in] FunctionTailcall2 *pFuncTailcall);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac9fe-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ac9fe-105">Parameters</span></span>  
 `pFuncEnter`  
 <span data-ttu-id="ac9fe-106">진행 [FunctionEnter2](functionenter2-function.md) 콜백으로 사용할 구현에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ac9fe-106">[in] A pointer to the implementation to be used as the [FunctionEnter2](functionenter2-function.md) callback.</span></span>  
  
 `pFuncLeave`  
 <span data-ttu-id="ac9fe-107">진행 [FunctionLeave2](functionleave2-function.md) 콜백으로 사용할 구현에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ac9fe-107">[in] A pointer to the implementation to be used as the [FunctionLeave2](functionleave2-function.md) callback.</span></span>  
  
 `pFuncTailcall`  
 <span data-ttu-id="ac9fe-108">진행 [FunctionTailcall2](functiontailcall2-function.md) 콜백으로 사용할 구현에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ac9fe-108">[in] A pointer to the implementation to be used as the [FunctionTailcall2](functiontailcall2-function.md) callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac9fe-109">설명</span><span class="sxs-lookup"><span data-stu-id="ac9fe-109">Remarks</span></span>  
 <span data-ttu-id="ac9fe-110">`SetEnterLeaveFunctionHooks2`메서드는 [ICorProfilerInfo:: SetEnterLeaveFunctionHooks](icorprofilerinfo-setenterleavefunctionhooks-method.md) 메서드와 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac9fe-110">The `SetEnterLeaveFunctionHooks2` method is similar to the [ICorProfilerInfo::SetEnterLeaveFunctionHooks](icorprofilerinfo-setenterleavefunctionhooks-method.md) method.</span></span> <span data-ttu-id="ac9fe-111">이전에는 enter/leave/tailcall 콜백의 최신 버전으로 사용할 함수를 지정 하 고 후자는 enter/leave/tailcall 콜백의 이전 버전으로 사용할 함수를 지정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac9fe-111">Use the former to specify functions to be used as the newer versions of the enter/leave/tailcall callbacks, and the latter to specify functions to be used as the older versions of the enter/leave/tailcall callbacks.</span></span>  
  
 <span data-ttu-id="ac9fe-112">한 번에 하나의 콜백 집합만 활성 상태일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac9fe-112">Only one set of callbacks may be active at a time.</span></span> <span data-ttu-id="ac9fe-113">따라서 프로파일러가 및를 모두 호출 하면 `ICorProfilerInfo::SetEnterLeaveFunctionHooks` `SetEnterLeaveFunctionHooks2` `SetEnterLeaveFunctionHooks2` 이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac9fe-113">Thus, if a profiler calls both `ICorProfilerInfo::SetEnterLeaveFunctionHooks` and `SetEnterLeaveFunctionHooks2`, `SetEnterLeaveFunctionHooks2` is used.</span></span>  
  
 <span data-ttu-id="ac9fe-114">`SetEnterLeaveFunctionHooks2`메서드는 프로파일러의 [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) 콜백에서만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac9fe-114">The `SetEnterLeaveFunctionHooks2` method may be called only from the profiler's [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac9fe-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ac9fe-115">Requirements</span></span>  
 <span data-ttu-id="ac9fe-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ac9fe-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac9fe-117">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ac9fe-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ac9fe-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac9fe-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac9fe-119">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac9fe-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac9fe-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ac9fe-120">See also</span></span>

- [<span data-ttu-id="ac9fe-121">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ac9fe-121">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="ac9fe-122">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ac9fe-122">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
