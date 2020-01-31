---
title: ICorProfilerCallback::UnmanagedToManagedTransition 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.UnmanagedToManagedTransition
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::UnmanagedToManagedTransition
helpviewer_keywords:
- ICorProfilerCallback::UnmanagedToManagedTransition method [.NET Framework profiling]
- UnmanagedToManagedTransition method [.NET Framework profiling]
ms.assetid: ade2cc01-9b81-4e09-a5f9-b3b9dda27e96
topic_type:
- apiref
ms.openlocfilehash: c381d4a85a1e836f1972060c8182dd698bb27550
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76870537"
---
# <a name="icorprofilercallbackunmanagedtomanagedtransition-method"></a><span data-ttu-id="ae1d5-102">ICorProfilerCallback::UnmanagedToManagedTransition 메서드</span><span class="sxs-lookup"><span data-stu-id="ae1d5-102">ICorProfilerCallback::UnmanagedToManagedTransition Method</span></span>
<span data-ttu-id="ae1d5-103">비관리 코드에서 관리 코드로의 전환이 발생 했음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ae1d5-103">Notifies the profiler that a transition from unmanaged code to managed code has occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae1d5-104">구문</span><span class="sxs-lookup"><span data-stu-id="ae1d5-104">Syntax</span></span>  
  
```cpp  
HRESULT UnmanagedToManagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae1d5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ae1d5-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="ae1d5-106">진행 호출 되는 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ae1d5-106">[in] The ID of the function that is being called.</span></span>  
  
 `reason`  
 <span data-ttu-id="ae1d5-107">진행 비관리 코드에서 관리 코드를 호출 하거나 관리 되는 함수에 의해 호출 된 관리 되지 않는 함수의 반환 때문에 전환이 발생 했는지 여부를 나타내는 [COR_PRF_TRANSITION_REASON](cor-prf-transition-reason-enumeration.md) 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ae1d5-107">[in] A value of the [COR_PRF_TRANSITION_REASON](cor-prf-transition-reason-enumeration.md) enumeration that indicates whether the transition occurred because of a call into managed code from unmanaged code, or because of a return from an unmanaged function called by a managed one.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae1d5-108">주의</span><span class="sxs-lookup"><span data-stu-id="ae1d5-108">Remarks</span></span>  
 <span data-ttu-id="ae1d5-109">`reason` 값이 COR_PRF_TRANSITION_RETURN 되 고 `functionId` null이 아닌 경우 함수 ID는 관리 되지 않는 함수의 함수 ID 이며 JIT (just-in-time) 컴파일러를 사용 하 여 컴파일되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae1d5-109">If the value of `reason` is COR_PRF_TRANSITION_RETURN and `functionId` is not null, the function ID is that of the unmanaged function, and will never have been compiled using the just-in-time (JIT) compiler.</span></span> <span data-ttu-id="ae1d5-110">관리 되지 않는 함수에는 이름 및 일부 메타 데이터와 같은 몇 가지 기본 정보가 연결 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae1d5-110">Unmanaged functions have some basic information associated with them, such as a name and some metadata.</span></span>  
  
 <span data-ttu-id="ae1d5-111">`reason` 값이 COR_PRF_TRANSITION_CALL 되는 경우 호출 된 함수 (관리 되는 함수)는 아직 JIT 컴파일되지 않았을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae1d5-111">If the value of `reason` is COR_PRF_TRANSITION_CALL, it may be possible that the called function (that is, the managed function) has not yet been JIT-compiled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae1d5-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ae1d5-112">Requirements</span></span>  
 <span data-ttu-id="ae1d5-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae1d5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae1d5-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ae1d5-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ae1d5-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae1d5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae1d5-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae1d5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae1d5-117">참조</span><span class="sxs-lookup"><span data-stu-id="ae1d5-117">See also</span></span>

- [<span data-ttu-id="ae1d5-118">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ae1d5-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="ae1d5-119">ManagedToUnmanagedTransition 메서드</span><span class="sxs-lookup"><span data-stu-id="ae1d5-119">ManagedToUnmanagedTransition Method</span></span>](icorprofilercallback-managedtounmanagedtransition-method.md)
- [<span data-ttu-id="ae1d5-120">C++에서 명시적 PInvoke 사용(DllImport 특성)</span><span class="sxs-lookup"><span data-stu-id="ae1d5-120">Using Explicit PInvoke in C++ (DllImport Attribute)</span></span>](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
- [<span data-ttu-id="ae1d5-121">C++ Interop 사용(암시적 PInvoke)</span><span class="sxs-lookup"><span data-stu-id="ae1d5-121">Using C++ Interop (Implicit PInvoke)</span></span>](/cpp/dotnet/using-cpp-interop-implicit-pinvoke)
