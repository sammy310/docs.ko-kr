---
title: ICorProfilerCallback::JITInlining 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITInlining
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITInlining
helpviewer_keywords:
- JITInlining method [.NET Framework profiling]
- ICorProfilerCallback::JITInlining method [.NET Framework profiling]
ms.assetid: c2f45801-dd38-4b78-b6b7-64397dc73f83
topic_type:
- apiref
ms.openlocfilehash: 62035d623d56f7521e0a599a13bc20778e3f18d1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449911"
---
# <a name="icorprofilercallbackjitinlining-method"></a><span data-ttu-id="47293-102">ICorProfilerCallback::JITInlining 메서드</span><span class="sxs-lookup"><span data-stu-id="47293-102">ICorProfilerCallback::JITInlining Method</span></span>
<span data-ttu-id="47293-103">JIT (just-in-time) 컴파일러가 다른 함수를 사용 하 여 함수를 삽입 하려고 함을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="47293-103">Notifies the profiler that the just-in-time (JIT) compiler is about to insert a function in line with another function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47293-104">구문</span><span class="sxs-lookup"><span data-stu-id="47293-104">Syntax</span></span>  
  
```cpp  
HRESULT JITInlining(  
    [in]  FunctionID callerId,  
    [in]  FunctionID calleeId,  
    [out] BOOL      *pfShouldInline);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47293-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="47293-105">Parameters</span></span>  
 `callerId`  
 <span data-ttu-id="47293-106">진행 `calleeId` 함수를 삽입할 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="47293-106">[in] The ID of the function into which the `calleeId` function will be inserted.</span></span>  
  
 `calleeId`  
 <span data-ttu-id="47293-107">진행 삽입할 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="47293-107">[in] The ID of the function to be inserted.</span></span>  
  
 `pfShouldInline`  
 <span data-ttu-id="47293-108">[out] 삽입을 수행할 수 있도록 `true` 합니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="47293-108">[out] `true` to allow the insertion to occur; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47293-109">주의</span><span class="sxs-lookup"><span data-stu-id="47293-109">Remarks</span></span>  
 <span data-ttu-id="47293-110">프로파일러는 `false` `pfShouldInline`를 설정 하 여 `calleeId` 함수가 `callerId` 함수에 삽입 되지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47293-110">The profiler can set `pfShouldInline` to `false` to prevent the `calleeId` function from being inserted into the `callerId` function.</span></span> <span data-ttu-id="47293-111">또한 프로파일러는 [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) 열거형의 COR_PRF_DISABLE_INLINING 값을 사용 하 여 인라인 삽입을 전역적으로 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47293-111">Also, the profiler can globally disable inline insertion by using the COR_PRF_DISABLE_INLINING value of the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="47293-112">인라인으로 삽입 된 함수는 시작 또는 종료에 대 한 이벤트를 발생 시 키 지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47293-112">Functions inserted inline do not raise events for entering or leaving.</span></span> <span data-ttu-id="47293-113">따라서 정확한 호출 그래프을 생성 하기 위해 프로파일러는 `false` `pfShouldInline` 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47293-113">Therefore, the profiler must set `pfShouldInline` to `false` in order to produce an accurate callgraph.</span></span> <span data-ttu-id="47293-114">인라인 삽입은 일반적으로 속도가 향상 되 고 삽입 된 메서드에 대 한 별도의 JIT 컴파일 이벤트 수가 줄어들기 때문에 `pfShouldInline`를 `false`로 설정 하면 성능에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="47293-114">Setting `pfShouldInline` to `false` will affect performance, because inline insertion typically increases speed and reduces the number of separate JIT compilation events for the inserted method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47293-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="47293-115">Requirements</span></span>  
 <span data-ttu-id="47293-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="47293-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47293-117">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="47293-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="47293-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47293-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="47293-119">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47293-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47293-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="47293-120">See also</span></span>

- [<span data-ttu-id="47293-121">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="47293-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
