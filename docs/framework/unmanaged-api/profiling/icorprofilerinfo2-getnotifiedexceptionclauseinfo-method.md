---
title: ICorProfilerInfo2::GetNotifiedExceptionClauseInfo 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetNotifiedExceptionClauseInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetNotifiedExceptionClauseInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetNotifiedExceptionCaluseInfo method [.NET Framework profiling]
- GetNotifiedExceptionCaluseInfo method [.NET Framework profiling]
ms.assetid: f9594a7e-cb0c-4c48-accb-29f762aa0c21
topic_type:
- apiref
ms.openlocfilehash: b0d94f5004da85caf0460e8f1d1b2d964944b045
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727070"
---
# <a name="icorprofilerinfo2getnotifiedexceptionclauseinfo-method"></a><span data-ttu-id="7e200-102">ICorProfilerInfo2::GetNotifiedExceptionClauseInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="7e200-102">ICorProfilerInfo2::GetNotifiedExceptionClauseInfo Method</span></span>

<span data-ttu-id="7e200-103">`catch` / `finally` / `filter` 실행 되거나 방금 실행 된 예외 절 ()에 대 한 기본 주소 및 프레임 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7e200-103">Gets the native address and frame information for the exception clause (`catch`/`finally`/`filter`) that is about to be run or has just been run.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e200-104">구문</span><span class="sxs-lookup"><span data-stu-id="7e200-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNotifiedExceptionClauseInfo(  
    [out] COR_PRF_EX_CLAUSE_INFO *pinfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e200-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7e200-105">Parameters</span></span>  

 `pinfo`  
 <span data-ttu-id="7e200-106">제한이 현재 예외 절 인스턴스와 관련 프레임을 설명 하는 [COR_PRF_EX_CLAUSE_INFO](cor-prf-ex-clause-info-structure.md) 구조체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7e200-106">[out] A pointer to a [COR_PRF_EX_CLAUSE_INFO](cor-prf-ex-clause-info-structure.md) structure that describes the current exception clause instance and its associated frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e200-107">설명</span><span class="sxs-lookup"><span data-stu-id="7e200-107">Remarks</span></span>  

 <span data-ttu-id="7e200-108">예외 알림이 수신 되 면는 `GetNotifiedExceptionClauseInfo` 실행 될 예외 절 ()에 대 한 기본 주소 및 프레임 정보를 가져오는 데 사용할 수 있습니다 `catch` / `finally` / `filter` ([ICorProfilerCallback:: ExceptionCatcherEnter](icorprofilercallback-exceptioncatcherenter-method.md), [ICorProfilerCallback:: ExceptionUnwindFinallyEnter](icorprofilercallback-exceptionunwindfinallyenter-method.md)또는 [ICorProfilerCallback:: exceptionsearchfilterenter](icorprofilercallback-exceptionsearchfilterenter-method.md) 콜백을 프로파일러에서 수신 했거나, 실행 된 직후 ([ICorProfilerCallback:: ExceptionCatcherLeave](icorprofilercallback-exceptioncatcherleave-method.md), [ICorProfilerCallback:: ExceptionUnwindFinallyLeave](icorprofilercallback-exceptionunwindfinallyleave-method.md)또는 [ICorProfilerCallback:: exceptionsearchfilterenter](icorprofilercallback-exceptionsearchfilterleave-method.md) 콜백을 프로파일러에서 수신 했습니다.)</span><span class="sxs-lookup"><span data-stu-id="7e200-108">When an exception notification is received, `GetNotifiedExceptionClauseInfo` can be used to get the native address and frame information for the exception clause (`catch`/`finally`/`filter`) that is about to be run ([ICorProfilerCallback::ExceptionCatcherEnter](icorprofilercallback-exceptioncatcherenter-method.md), [ICorProfilerCallback::ExceptionUnwindFinallyEnter](icorprofilercallback-exceptionunwindfinallyenter-method.md), or [ICorProfilerCallback::ExceptionSearchFilterEnter](icorprofilercallback-exceptionsearchfilterenter-method.md) callback is received by the profiler) or has just been run ([ICorProfilerCallback::ExceptionCatcherLeave](icorprofilercallback-exceptioncatcherleave-method.md), [ICorProfilerCallback::ExceptionUnwindFinallyLeave](icorprofilercallback-exceptionunwindfinallyleave-method.md), or [ICorProfilerCallback::ExceptionSearchFilterLeave](icorprofilercallback-exceptionsearchfilterleave-method.md) callback is received by the profiler).</span></span>  
  
 <span data-ttu-id="7e200-109">이 호출은 일치 하는 Leave 콜백이 수신 되거나 현재 절에서 중첩 된 예외가 throw 될 때까지 위의 Enter 콜백 중 하나를 실행 한 후 언제 든 지 수행할 수 있습니다 .이 경우에는 해당 절에 대 한 Leave 알림이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7e200-109">This call can be made at any time after one of the Enter callbacks above until either the matching Leave callback is received or a nested exception is thrown in the current clause, in which case there is no Leave notification for that clause.</span></span> <span data-ttu-id="7e200-110">Throw 된 예외가 예외 절을 이스케이프 하는 것은 불가능 `filter` 하므로이 경우 항상 Leave 알림이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e200-110">Note that it is not possible for a thrown exception to escape a `filter` exception clause, so there is always a Leave notification in that case.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e200-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7e200-111">Requirements</span></span>  

 <span data-ttu-id="7e200-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7e200-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e200-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7e200-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7e200-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e200-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7e200-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e200-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e200-116">참조</span><span class="sxs-lookup"><span data-stu-id="7e200-116">See also</span></span>

- [<span data-ttu-id="7e200-117">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7e200-117">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="7e200-118">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7e200-118">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
