---
title: CorDebugStepReason 열거형
ms.date: 03/30/2017
api_name:
- CorDebugStepReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugStepReason
helpviewer_keywords:
- CorDebugStepReason enumeration [.NET Framework debugging]
ms.assetid: fe248069-b33c-48e1-a777-06ac9b239c54
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d9dc94689083d79858319387747eb9dafe8b2f6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739568"
---
# <a name="cordebugstepreason-enumeration"></a><span data-ttu-id="dc366-102">CorDebugStepReason 열거형</span><span class="sxs-lookup"><span data-stu-id="dc366-102">CorDebugStepReason Enumeration</span></span>
<span data-ttu-id="dc366-103">개별 단계의 결과를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dc366-103">Indicates the outcome of an individual step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc366-104">구문</span><span class="sxs-lookup"><span data-stu-id="dc366-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugStepReason {  
    STEP_NORMAL,  
    STEP_RETURN,  
    STEP_CALL,  
    STEP_EXCEPTION_FILTER,  
    STEP_EXCEPTION_HANDLER,  
    STEP_INTERCEPT,  
    STEP_EXIT  
} CorDebugStepReason;  
```  
  
## <a name="members"></a><span data-ttu-id="dc366-105">멤버</span><span class="sxs-lookup"><span data-stu-id="dc366-105">Members</span></span>  
  
|<span data-ttu-id="dc366-106">멤버</span><span class="sxs-lookup"><span data-stu-id="dc366-106">Member</span></span>|<span data-ttu-id="dc366-107">Description</span><span class="sxs-lookup"><span data-stu-id="dc366-107">Description</span></span>|  
|------------|-----------------|  
|`STEP_NORMAL`|<span data-ttu-id="dc366-108">단계별 실행는 동일한 함수 내에서 정상적으로 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc366-108">Stepping completed normally, within the same function.</span></span>|  
|`STEP_RETURN`|<span data-ttu-id="dc366-109">단계별 함수 반환 후 정상적으로 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc366-109">Stepping continued normally, after the function returned.</span></span>|  
|`STEP_CALL`|<span data-ttu-id="dc366-110">단계별 실행이 새로 호출 된 함수의 시작 부분에 정상적으로 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc366-110">Stepping continued normally, at the beginning of a newly called function.</span></span>|  
|`STEP_EXCEPTION_FILTER`|<span data-ttu-id="dc366-111">예외가 생성 되었습니다 및 컨트롤 예외 필터에 전달 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dc366-111">An exception was generated and control was passed to an exception filter.</span></span>|  
|`STEP_EXCEPTION_HANDLER`|<span data-ttu-id="dc366-112">예외가 생성 되었습니다 및 컨트롤은 예외 처리기로 전달 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dc366-112">An exception was generated and control was passed to an exception handler.</span></span>|  
|`STEP_INTERCEPT`|<span data-ttu-id="dc366-113">컨트롤은 인터셉터로 전달 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dc366-113">Control was passed to an interceptor.</span></span>|  
|`STEP_EXIT`|<span data-ttu-id="dc366-114">단계를 완료 하기 전에 스레드가 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc366-114">The thread exited before the step was completed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dc366-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dc366-115">Requirements</span></span>  
 <span data-ttu-id="dc366-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="dc366-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc366-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dc366-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dc366-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dc366-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc366-119">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc366-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc366-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="dc366-120">See also</span></span>

- [<span data-ttu-id="dc366-121">StepComplete 메서드</span><span class="sxs-lookup"><span data-stu-id="dc366-121">StepComplete Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md)
- [<span data-ttu-id="dc366-122">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="dc366-122">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
