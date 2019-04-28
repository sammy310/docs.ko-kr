---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5e12410ab9886055dca8c3f9103c1e56475c2d5e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775156"
---
# <a name="corprfexclauseinfo-structure"></a><span data-ttu-id="a6ad4-102">COR_PRF_EX_CLAUSE_INFO 구조체</span><span class="sxs-lookup"><span data-stu-id="a6ad4-102">COR_PRF_EX_CLAUSE_INFO Structure</span></span>
<span data-ttu-id="a6ad4-103">특정 예외 절 인스턴스 및 관련 프레임에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="a6ad4-103">Stores information about a specific exception clause instance and its associated frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6ad4-104">구문</span><span class="sxs-lookup"><span data-stu-id="a6ad4-104">Syntax</span></span>  
  
```  
typedef struct COR_PRF_EX_CLAUSE_INFO {  
    COR_PRF_CLAUSE_TYPE clauseType;  
    UINT_PTR programCounter;  
    UINT_PTR framePointer;  
    UINT_PTR shadowStackPointer;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="a6ad4-105">멤버</span><span class="sxs-lookup"><span data-stu-id="a6ad4-105">Members</span></span>  
  
|<span data-ttu-id="a6ad4-106">멤버</span><span class="sxs-lookup"><span data-stu-id="a6ad4-106">Member</span></span>|<span data-ttu-id="a6ad4-107">설명</span><span class="sxs-lookup"><span data-stu-id="a6ad4-107">Description</span></span>|  
|------------|-----------------|  
|`clauseType`|<span data-ttu-id="a6ad4-108">값을 [COR_PRF_CLAUSE_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md) 예외 절 방금 입력 한 코드 왼쪽의 형식을 지정 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="a6ad4-108">A value of the [COR_PRF_CLAUSE_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md) enumeration that specifies the type of exception clause the code just entered or left.</span></span>|  
|`programCounter`|<span data-ttu-id="a6ad4-109">절 처리기의 네이티브 진입점-X86 EIP 레지스터의 내용을 예를 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6ad4-109">The native entry point of the clause handler — for example, the contents of the X86 EIP register.</span></span>|  
|`framePointer`|<span data-ttu-id="a6ad4-110">절 처리기에 대 한 논리 프레임에 대 한 포인터-X86 EBP 레지스터의 내용을 예를 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6ad4-110">The pointer to the logical frame for the clause handler — for example, the contents of the X86 EBP register.</span></span>|  
|`shadowStackPointer`|<span data-ttu-id="a6ad4-111">섀도 스택 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a6ad4-111">The pointer to the shadow stack.</span></span> <span data-ttu-id="a6ad4-112">이 값은 BSP 레지스터의 내용 및 IA64에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6ad4-112">This value is the contents of the BSP register and applies only to IA64.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6ad4-113">설명</span><span class="sxs-lookup"><span data-stu-id="a6ad4-113">Remarks</span></span>  
 <span data-ttu-id="a6ad4-114">예외 알림을 받으면 [ICorProfilerInfo2::GetNotifiedExceptionClauseInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) 예외 절에 대 한 기본 주소와 프레임 정보를 가져오는 데 사용할 수 있습니다 (`catch` / `finally`/필터) 방금 실행 되거나 실행 될는 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6ad4-114">When an exception notification is received, [ICorProfilerInfo2::GetNotifiedExceptionClauseInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) can be used to get the native address and frame information for the exception clause (`catch`/`finally`/filter) that is about to be run or has just been run.</span></span>  
  
 <span data-ttu-id="a6ad4-115">Exception 절 실행에는 CLR (공용 언어 런타임)에서 이러한 콜백을 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6ad4-115">Execution of an exception clause involves these callbacks from the common language runtime (CLR):</span></span>  
  
- [<span data-ttu-id="a6ad4-116">ICorProfilerCallback::ExceptionCatcherEnter</span><span class="sxs-lookup"><span data-stu-id="a6ad4-116">ICorProfilerCallback::ExceptionCatcherEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)  
  
- [<span data-ttu-id="a6ad4-117">ICorProfilerCallback::ExceptionUnwindFinallyEnter</span><span class="sxs-lookup"><span data-stu-id="a6ad4-117">ICorProfilerCallback::ExceptionUnwindFinallyEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)  
  
- [<span data-ttu-id="a6ad4-118">ICorProfilerCallback::ExceptionSearchFilterEnter</span><span class="sxs-lookup"><span data-stu-id="a6ad4-118">ICorProfilerCallback::ExceptionSearchFilterEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)  
  
- [<span data-ttu-id="a6ad4-119">ICorProfilerCallback::ExceptionCatcherLeave</span><span class="sxs-lookup"><span data-stu-id="a6ad4-119">ICorProfilerCallback::ExceptionCatcherLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)  
  
- [<span data-ttu-id="a6ad4-120">ICorProfilerCallback::ExceptionUnwindFinallyLeave</span><span class="sxs-lookup"><span data-stu-id="a6ad4-120">ICorProfilerCallback::ExceptionUnwindFinallyLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)  
  
- [<span data-ttu-id="a6ad4-121">ICorProfilerCallback::ExceptionSearchFilterLeave</span><span class="sxs-lookup"><span data-stu-id="a6ad4-121">ICorProfilerCallback::ExceptionSearchFilterLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)  
  
## <a name="requirements"></a><span data-ttu-id="a6ad4-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a6ad4-122">Requirements</span></span>  
 <span data-ttu-id="a6ad4-123">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a6ad4-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6ad4-124">**헤더:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="a6ad4-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="a6ad4-125">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6ad4-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6ad4-126">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6ad4-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6ad4-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="a6ad4-127">See also</span></span>

- [<span data-ttu-id="a6ad4-128">프로파일링 구조체</span><span class="sxs-lookup"><span data-stu-id="a6ad4-128">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
