---
title: ICorProfilerInfo::SetFunctionIDMapper 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetFunctionIDMapper
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetFunctionIDMapper
helpviewer_keywords:
- ICorProfilerInfo::SetFunctionIDMapper method [.NET Framework profiling]
- SetFunctionIDMapper method [.NET Framework profiling]
ms.assetid: 1a6e5dae-d366-4497-9c02-7b5b1f43f9ec
topic_type:
- apiref
ms.openlocfilehash: 52ab9a089b5def4f3db2f99abc5a718d66cca739
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863454"
---
# <a name="icorprofilerinfosetfunctionidmapper-method"></a><span data-ttu-id="6b769-102">ICorProfilerInfo::SetFunctionIDMapper 메서드</span><span class="sxs-lookup"><span data-stu-id="6b769-102">ICorProfilerInfo::SetFunctionIDMapper Method</span></span>
<span data-ttu-id="6b769-103">`FunctionID` 값을 대체 값에 매핑하기 위해 호출되는 프로파일러 구현 함수를 지정합니다. 대체 값은 프로파일러의 함수 진입점/종료점 후크에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b769-103">Specifies the profiler-implemented function that will be called to map `FunctionID` values to alternative values, which are passed to the profiler's function entry/exit hooks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b769-104">구문</span><span class="sxs-lookup"><span data-stu-id="6b769-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFunctionIDMapper (  
    [in] FunctionIDMapper *pFunc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b769-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6b769-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="6b769-106">진행 `FunctionID` 값을 대체 값으로 매핑하기 위해 호출 되는 [Functionidmapper](functionidmapper-function.md) 구현에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6b769-106">[in] A pointer to the [FunctionIDMapper](functionidmapper-function.md) implementation that will be called to map the `FunctionID` values to their alternative values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b769-107">주의</span><span class="sxs-lookup"><span data-stu-id="6b769-107">Remarks</span></span>  
 <span data-ttu-id="6b769-108">`FunctionID` 값에 대 한 대안은 [ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) 메서드에 지정 된 프로파일러의 함수 진입/종료 후크 ([FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md)및 [FunctionTailcall2](functiontailcall2-function.md))에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b769-108">The alternatives for the `FunctionID` values will be passed to the profiler's function entry/exit hooks ([FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md), and [FunctionTailcall2](functiontailcall2-function.md)) that are specified by the [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) method.</span></span>  
  
 <span data-ttu-id="6b769-109">`FunctionIDMapper`은 한 번만 설정할 수 있으며, [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) 콜백에서 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6b769-109">The `FunctionIDMapper` can be set only once and it is recommended that you set it in the [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b769-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6b769-110">Requirements</span></span>  
 <span data-ttu-id="6b769-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6b769-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b769-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6b769-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6b769-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b769-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b769-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b769-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b769-115">참조</span><span class="sxs-lookup"><span data-stu-id="6b769-115">See also</span></span>

- [<span data-ttu-id="6b769-116">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6b769-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
