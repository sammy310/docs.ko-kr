---
description: '다음에 대 한 자세한 정보: COR_PRF_EX_CLAUSE_INFO 구조체'
title: COR_PRF_EX_CLAUSE_INFO 구조체
ms.date: 03/30/2017
api_name:
- COR_PRF_EX_CLAUSE_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_EX_CLAUSE_INFO
helpviewer_keywords:
- COR_PRF_EX_CLAUSE_INFO structure [.NET Framework profiling]
ms.assetid: 7d0d6fb7-bc9d-40f0-8163-c0d162eaba7d
topic_type:
- apiref
ms.openlocfilehash: af8d404e55a8996abc69923924e87c95e3c5eae8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649210"
---
# <a name="cor_prf_ex_clause_info-structure"></a><span data-ttu-id="aaa95-103">COR_PRF_EX_CLAUSE_INFO 구조체</span><span class="sxs-lookup"><span data-stu-id="aaa95-103">COR_PRF_EX_CLAUSE_INFO Structure</span></span>

<span data-ttu-id="aaa95-104">특정 예외 절 인스턴스 및 관련 프레임에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-104">Stores information about a specific exception clause instance and its associated frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aaa95-105">구문</span><span class="sxs-lookup"><span data-stu-id="aaa95-105">Syntax</span></span>  
  
```cpp  
typedef struct COR_PRF_EX_CLAUSE_INFO {  
    COR_PRF_CLAUSE_TYPE clauseType;  
    UINT_PTR programCounter;  
    UINT_PTR framePointer;  
    UINT_PTR shadowStackPointer;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="aaa95-106">구성원</span><span class="sxs-lookup"><span data-stu-id="aaa95-106">Members</span></span>  
  
|<span data-ttu-id="aaa95-107">멤버</span><span class="sxs-lookup"><span data-stu-id="aaa95-107">Member</span></span>|<span data-ttu-id="aaa95-108">설명</span><span class="sxs-lookup"><span data-stu-id="aaa95-108">Description</span></span>|  
|------------|-----------------|  
|`clauseType`|<span data-ttu-id="aaa95-109">코드에서 방금 입력 하거나 남겨진 예외 절의 유형을 지정 하는 [COR_PRF_CLAUSE_TYPE](cor-prf-clause-type-enumeration.md) 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-109">A value of the [COR_PRF_CLAUSE_TYPE](cor-prf-clause-type-enumeration.md) enumeration that specifies the type of exception clause the code just entered or left.</span></span>|  
|`programCounter`|<span data-ttu-id="aaa95-110">절 처리기의 기본 진입점입니다 (예: X86 EIP 레지스터의 내용).</span><span class="sxs-lookup"><span data-stu-id="aaa95-110">The native entry point of the clause handler — for example, the contents of the X86 EIP register.</span></span>|  
|`framePointer`|<span data-ttu-id="aaa95-111">절 처리기의 논리적 프레임에 대 한 포인터입니다 (예: X86 EBP 레지스터의 내용).</span><span class="sxs-lookup"><span data-stu-id="aaa95-111">The pointer to the logical frame for the clause handler — for example, the contents of the X86 EBP register.</span></span>|  
|`shadowStackPointer`|<span data-ttu-id="aaa95-112">그림자 스택에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-112">The pointer to the shadow stack.</span></span> <span data-ttu-id="aaa95-113">이 값은 BSP 레지스터의 내용이 며 IA64에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-113">This value is the contents of the BSP register and applies only to IA64.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aaa95-114">설명</span><span class="sxs-lookup"><span data-stu-id="aaa95-114">Remarks</span></span>  

 <span data-ttu-id="aaa95-115">예외 알림이 수신 되 면 [ICorProfilerInfo2:: GetNotifiedExceptionClauseInfo](icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) 를 사용 하 여 `catch` / `finally` 실행 되거나 방금 실행 된 예외 절 (/profilter)의 기본 주소 및 프레임 정보를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-115">When an exception notification is received, [ICorProfilerInfo2::GetNotifiedExceptionClauseInfo](icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) can be used to get the native address and frame information for the exception clause (`catch`/`finally`/filter) that is about to be run or has just been run.</span></span>  
  
 <span data-ttu-id="aaa95-116">예외 절의 실행은 CLR (공용 언어 런타임)의 이러한 콜백과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aaa95-116">Execution of an exception clause involves these callbacks from the common language runtime (CLR):</span></span>  
  
- [<span data-ttu-id="aaa95-117">ICorProfilerCallback:: ExceptionCatcherEnter</span><span class="sxs-lookup"><span data-stu-id="aaa95-117">ICorProfilerCallback::ExceptionCatcherEnter</span></span>](icorprofilercallback-exceptioncatcherenter-method.md)  
  
- [<span data-ttu-id="aaa95-118">ICorProfilerCallback:: ExceptionUnwindFinallyEnter</span><span class="sxs-lookup"><span data-stu-id="aaa95-118">ICorProfilerCallback::ExceptionUnwindFinallyEnter</span></span>](icorprofilercallback-exceptionunwindfinallyenter-method.md)  
  
- [<span data-ttu-id="aaa95-119">ICorProfilerCallback:: ExceptionSearchFilterEnter</span><span class="sxs-lookup"><span data-stu-id="aaa95-119">ICorProfilerCallback::ExceptionSearchFilterEnter</span></span>](icorprofilercallback-exceptionsearchfilterenter-method.md)  
  
- [<span data-ttu-id="aaa95-120">ICorProfilerCallback:: ExceptionCatcherLeave</span><span class="sxs-lookup"><span data-stu-id="aaa95-120">ICorProfilerCallback::ExceptionCatcherLeave</span></span>](icorprofilercallback-exceptioncatcherleave-method.md)  
  
- [<span data-ttu-id="aaa95-121">ICorProfilerCallback:: ExceptionUnwindFinallyLeave</span><span class="sxs-lookup"><span data-stu-id="aaa95-121">ICorProfilerCallback::ExceptionUnwindFinallyLeave</span></span>](icorprofilercallback-exceptionunwindfinallyleave-method.md)  
  
- [<span data-ttu-id="aaa95-122">ICorProfilerCallback:: ExceptionSearchFilterLeave</span><span class="sxs-lookup"><span data-stu-id="aaa95-122">ICorProfilerCallback::ExceptionSearchFilterLeave</span></span>](icorprofilercallback-exceptionsearchfilterleave-method.md)  
  
## <a name="requirements"></a><span data-ttu-id="aaa95-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="aaa95-123">Requirements</span></span>  

 <span data-ttu-id="aaa95-124">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aaa95-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aaa95-125">**헤더:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="aaa95-125">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="aaa95-126">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aaa95-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aaa95-127">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aaa95-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaa95-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aaa95-128">See also</span></span>

- [<span data-ttu-id="aaa95-129">프로파일링 구조체</span><span class="sxs-lookup"><span data-stu-id="aaa95-129">Profiling Structures</span></span>](profiling-structures.md)
