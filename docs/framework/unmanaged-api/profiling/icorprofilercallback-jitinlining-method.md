---
description: '자세히 알아보기: ICorProfilerCallback:: JITInlining 메서드'
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
ms.openlocfilehash: 2bd6c48180b9484ef90b6afb505c8171aff57aa4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99705644"
---
# <a name="icorprofilercallbackjitinlining-method"></a><span data-ttu-id="0c39f-103">ICorProfilerCallback::JITInlining 메서드</span><span class="sxs-lookup"><span data-stu-id="0c39f-103">ICorProfilerCallback::JITInlining Method</span></span>

<span data-ttu-id="0c39f-104">JIT (just-in-time) 컴파일러가 다른 함수를 사용 하 여 함수를 삽입 하려고 함을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="0c39f-104">Notifies the profiler that the just-in-time (JIT) compiler is about to insert a function in line with another function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c39f-105">구문</span><span class="sxs-lookup"><span data-stu-id="0c39f-105">Syntax</span></span>  
  
```cpp  
HRESULT JITInlining(  
    [in]  FunctionID callerId,  
    [in]  FunctionID calleeId,  
    [out] BOOL      *pfShouldInline);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c39f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0c39f-106">Parameters</span></span>  

 `callerId`  
 <span data-ttu-id="0c39f-107">진행 함수가 삽입 되는 함수의 ID입니다 `calleeId` .</span><span class="sxs-lookup"><span data-stu-id="0c39f-107">[in] The ID of the function into which the `calleeId` function will be inserted.</span></span>  
  
 `calleeId`  
 <span data-ttu-id="0c39f-108">진행 삽입할 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0c39f-108">[in] The ID of the function to be inserted.</span></span>  
  
 `pfShouldInline`  
 <span data-ttu-id="0c39f-109">[out] `true` 삽입이 발생할 수 있도록 하려면 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="0c39f-109">[out] `true` to allow the insertion to occur; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c39f-110">설명</span><span class="sxs-lookup"><span data-stu-id="0c39f-110">Remarks</span></span>  

 <span data-ttu-id="0c39f-111">프로파일러가 함수에 `pfShouldInline` `false` 삽입 되지 않도록 프로파일러를로 설정할 수 있습니다 `calleeId` `callerId` .</span><span class="sxs-lookup"><span data-stu-id="0c39f-111">The profiler can set `pfShouldInline` to `false` to prevent the `calleeId` function from being inserted into the `callerId` function.</span></span> <span data-ttu-id="0c39f-112">또한 프로파일러는 [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) 열거형의 COR_PRF_DISABLE_INLINING 값을 사용 하 여 인라인 삽입을 전역적으로 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c39f-112">Also, the profiler can globally disable inline insertion by using the COR_PRF_DISABLE_INLINING value of the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="0c39f-113">인라인으로 삽입 된 함수는 시작 또는 종료에 대 한 이벤트를 발생 시 키 지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0c39f-113">Functions inserted inline do not raise events for entering or leaving.</span></span> <span data-ttu-id="0c39f-114">따라서 `pfShouldInline` 정확한 호출 그래프을 생성 하기 위해 프로파일러가로 설정 되어야 합니다 `false` .</span><span class="sxs-lookup"><span data-stu-id="0c39f-114">Therefore, the profiler must set `pfShouldInline` to `false` in order to produce an accurate callgraph.</span></span> <span data-ttu-id="0c39f-115">`pfShouldInline` `false` 인라인 삽입은 일반적으로 속도가 향상 되 고 삽입 된 메서드에 대 한 개별 JIT 컴파일 이벤트 수가 줄어들기 때문에로 설정 하면 성능에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0c39f-115">Setting `pfShouldInline` to `false` will affect performance, because inline insertion typically increases speed and reduces the number of separate JIT compilation events for the inserted method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c39f-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0c39f-116">Requirements</span></span>  

 <span data-ttu-id="0c39f-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0c39f-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c39f-118">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0c39f-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0c39f-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c39f-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c39f-120">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c39f-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c39f-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0c39f-121">See also</span></span>

- [<span data-ttu-id="0c39f-122">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0c39f-122">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
