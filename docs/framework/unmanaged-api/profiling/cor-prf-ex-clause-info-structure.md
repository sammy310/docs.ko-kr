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
ms.openlocfilehash: df4bfe69b22439073342693a03376a0b506f9c70
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428378"
---
# <a name="cor_prf_ex_clause_info-structure"></a><span data-ttu-id="0a2e5-102">COR_PRF_EX_CLAUSE_INFO 구조체</span><span class="sxs-lookup"><span data-stu-id="0a2e5-102">COR_PRF_EX_CLAUSE_INFO Structure</span></span>
<span data-ttu-id="0a2e5-103">특정 예외 절 인스턴스 및 관련 프레임에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2e5-103">Stores information about a specific exception clause instance and its associated frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a2e5-104">구문</span><span class="sxs-lookup"><span data-stu-id="0a2e5-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_PRF_EX_CLAUSE_INFO {  
    COR_PRF_CLAUSE_TYPE clauseType;  
    UINT_PTR programCounter;  
    UINT_PTR framePointer;  
    UINT_PTR shadowStackPointer;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="0a2e5-105">멤버</span><span class="sxs-lookup"><span data-stu-id="0a2e5-105">Members</span></span>  
  
|<span data-ttu-id="0a2e5-106">멤버</span><span class="sxs-lookup"><span data-stu-id="0a2e5-106">Member</span></span>|<span data-ttu-id="0a2e5-107">설명</span><span class="sxs-lookup"><span data-stu-id="0a2e5-107">Description</span></span>|  
|------------|-----------------|  
|`clauseType`|<span data-ttu-id="0a2e5-108">A value of the [COR_PRF_CLAUSE_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md) enumeration that specifies the type of exception clause the code just entered or left.</span><span class="sxs-lookup"><span data-stu-id="0a2e5-108">A value of the [COR_PRF_CLAUSE_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md) enumeration that specifies the type of exception clause the code just entered or left.</span></span>|  
|`programCounter`|<span data-ttu-id="0a2e5-109">The native entry point of the clause handler — for example, the contents of the X86 EIP register.</span><span class="sxs-lookup"><span data-stu-id="0a2e5-109">The native entry point of the clause handler — for example, the contents of the X86 EIP register.</span></span>|  
|`framePointer`|<span data-ttu-id="0a2e5-110">The pointer to the logical frame for the clause handler — for example, the contents of the X86 EBP register.</span><span class="sxs-lookup"><span data-stu-id="0a2e5-110">The pointer to the logical frame for the clause handler — for example, the contents of the X86 EBP register.</span></span>|  
|`shadowStackPointer`|<span data-ttu-id="0a2e5-111">The pointer to the shadow stack.</span><span class="sxs-lookup"><span data-stu-id="0a2e5-111">The pointer to the shadow stack.</span></span> <span data-ttu-id="0a2e5-112">This value is the contents of the BSP register and applies only to IA64.</span><span class="sxs-lookup"><span data-stu-id="0a2e5-112">This value is the contents of the BSP register and applies only to IA64.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0a2e5-113">주의</span><span class="sxs-lookup"><span data-stu-id="0a2e5-113">Remarks</span></span>  
 <span data-ttu-id="0a2e5-114">When an exception notification is received, [ICorProfilerInfo2::GetNotifiedExceptionClauseInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) can be used to get the native address and frame information for the exception clause (`catch`/`finally`/filter) that is about to be run or has just been run.</span><span class="sxs-lookup"><span data-stu-id="0a2e5-114">When an exception notification is received, [ICorProfilerInfo2::GetNotifiedExceptionClauseInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) can be used to get the native address and frame information for the exception clause (`catch`/`finally`/filter) that is about to be run or has just been run.</span></span>  
  
 <span data-ttu-id="0a2e5-115">Execution of an exception clause involves these callbacks from the common language runtime (CLR):</span><span class="sxs-lookup"><span data-stu-id="0a2e5-115">Execution of an exception clause involves these callbacks from the common language runtime (CLR):</span></span>  
  
- [<span data-ttu-id="0a2e5-116">ICorProfilerCallback::ExceptionCatcherEnter</span><span class="sxs-lookup"><span data-stu-id="0a2e5-116">ICorProfilerCallback::ExceptionCatcherEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)  
  
- [<span data-ttu-id="0a2e5-117">ICorProfilerCallback::ExceptionUnwindFinallyEnter</span><span class="sxs-lookup"><span data-stu-id="0a2e5-117">ICorProfilerCallback::ExceptionUnwindFinallyEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)  
  
- [<span data-ttu-id="0a2e5-118">ICorProfilerCallback::ExceptionSearchFilterEnter</span><span class="sxs-lookup"><span data-stu-id="0a2e5-118">ICorProfilerCallback::ExceptionSearchFilterEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)  
  
- [<span data-ttu-id="0a2e5-119">ICorProfilerCallback::ExceptionCatcherLeave</span><span class="sxs-lookup"><span data-stu-id="0a2e5-119">ICorProfilerCallback::ExceptionCatcherLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)  
  
- [<span data-ttu-id="0a2e5-120">ICorProfilerCallback::ExceptionUnwindFinallyLeave</span><span class="sxs-lookup"><span data-stu-id="0a2e5-120">ICorProfilerCallback::ExceptionUnwindFinallyLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)  
  
- [<span data-ttu-id="0a2e5-121">ICorProfilerCallback::ExceptionSearchFilterLeave</span><span class="sxs-lookup"><span data-stu-id="0a2e5-121">ICorProfilerCallback::ExceptionSearchFilterLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)  
  
## <a name="requirements"></a><span data-ttu-id="0a2e5-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0a2e5-122">Requirements</span></span>  
 <span data-ttu-id="0a2e5-123">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0a2e5-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a2e5-124">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="0a2e5-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="0a2e5-125">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0a2e5-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0a2e5-126">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a2e5-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a2e5-127">참조</span><span class="sxs-lookup"><span data-stu-id="0a2e5-127">See also</span></span>

- [<span data-ttu-id="0a2e5-128">프로파일링 구조체</span><span class="sxs-lookup"><span data-stu-id="0a2e5-128">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
