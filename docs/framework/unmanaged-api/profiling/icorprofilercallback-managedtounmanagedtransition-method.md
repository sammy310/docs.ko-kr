---
title: ICorProfilerCallback::ManagedToUnmanagedTransition 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ManagedToUnmanagedTransition
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ManagedToUnmanagedTransition
helpviewer_keywords:
- ManagedToUnmanagedTransition method [.NET Framework profiling]
- ICorProfilerCallback::ManagedToUnmanagedTransition method [.NET Framework profiling]
ms.assetid: ef3cd619-912d-40c5-a449-03ba02a39ee7
topic_type:
- apiref
ms.openlocfilehash: f4f5871bdd7adf11fcc811fd40c62e3027b8e607
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426180"
---
# <a name="icorprofilercallbackmanagedtounmanagedtransition-method"></a><span data-ttu-id="01e5b-102">ICorProfilerCallback::ManagedToUnmanagedTransition 메서드</span><span class="sxs-lookup"><span data-stu-id="01e5b-102">ICorProfilerCallback::ManagedToUnmanagedTransition Method</span></span>
<span data-ttu-id="01e5b-103">Notifies the profiler that a transition from managed code to unmanaged code has occurred.</span><span class="sxs-lookup"><span data-stu-id="01e5b-103">Notifies the profiler that a transition from managed code to unmanaged code has occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01e5b-104">구문</span><span class="sxs-lookup"><span data-stu-id="01e5b-104">Syntax</span></span>  
  
```cpp  
HRESULT ManagedToUnmanagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01e5b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="01e5b-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="01e5b-106">[in] The ID of the function that is being called.</span><span class="sxs-lookup"><span data-stu-id="01e5b-106">[in] The ID of the function that is being called.</span></span>  
  
 `reason`  
 <span data-ttu-id="01e5b-107">[in] A value of the [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) enumeration that indicates whether the transition occurred because of a call into unmanaged code from managed code, or because of a return from a managed function called by an unmanaged one.</span><span class="sxs-lookup"><span data-stu-id="01e5b-107">[in] A value of the [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) enumeration that indicates whether the transition occurred because of a call into unmanaged code from managed code, or because of a return from a managed function called by an unmanaged one.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01e5b-108">주의</span><span class="sxs-lookup"><span data-stu-id="01e5b-108">Remarks</span></span>  
 <span data-ttu-id="01e5b-109">If the value of `reason` is COR_PRF_TRANSITION_CALL, the function ID is that of the unmanaged function, which will never have been compiled using the just-in-time compiler.</span><span class="sxs-lookup"><span data-stu-id="01e5b-109">If the value of `reason` is COR_PRF_TRANSITION_CALL, the function ID is that of the unmanaged function, which will never have been compiled using the just-in-time compiler.</span></span> <span data-ttu-id="01e5b-110">Unmanaged functions have basic information associated with them, such as a name and some metadata.</span><span class="sxs-lookup"><span data-stu-id="01e5b-110">Unmanaged functions have basic information associated with them, such as a name and some metadata.</span></span> <span data-ttu-id="01e5b-111">If the unmanaged function was called by using implicit platform invoke (PInvoke), the runtime cannot determine the destination of the call and the value of `functionId` will be null.</span><span class="sxs-lookup"><span data-stu-id="01e5b-111">If the unmanaged function was called by using implicit platform invoke (PInvoke), the runtime cannot determine the destination of the call and the value of `functionId` will be null.</span></span> <span data-ttu-id="01e5b-112">For more information on implicit PInvoke, see [Using C++ Interop (Implicit PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke).</span><span class="sxs-lookup"><span data-stu-id="01e5b-112">For more information on implicit PInvoke, see [Using C++ Interop (Implicit PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01e5b-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="01e5b-113">Requirements</span></span>  
 <span data-ttu-id="01e5b-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="01e5b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01e5b-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="01e5b-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="01e5b-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="01e5b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="01e5b-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01e5b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01e5b-118">참조</span><span class="sxs-lookup"><span data-stu-id="01e5b-118">See also</span></span>

- [<span data-ttu-id="01e5b-119">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="01e5b-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="01e5b-120">UnmanagedToManagedTransition 메서드</span><span class="sxs-lookup"><span data-stu-id="01e5b-120">UnmanagedToManagedTransition Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md)
- [<span data-ttu-id="01e5b-121">C++에서 명시적 PInvoke 사용(DllImport 특성)</span><span class="sxs-lookup"><span data-stu-id="01e5b-121">Using Explicit PInvoke in C++ (DllImport Attribute)</span></span>](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
