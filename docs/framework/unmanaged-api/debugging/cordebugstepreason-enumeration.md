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
ms.openlocfilehash: 288d7bfdf18be5cef032227c537032966fa68df4
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795705"
---
# <a name="cordebugstepreason-enumeration"></a><span data-ttu-id="49cb3-102">CorDebugStepReason 열거형</span><span class="sxs-lookup"><span data-stu-id="49cb3-102">CorDebugStepReason Enumeration</span></span>
<span data-ttu-id="49cb3-103">개별 단계의 결과를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="49cb3-103">Indicates the outcome of an individual step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49cb3-104">구문</span><span class="sxs-lookup"><span data-stu-id="49cb3-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="49cb3-105">구성원</span><span class="sxs-lookup"><span data-stu-id="49cb3-105">Members</span></span>  
  
|<span data-ttu-id="49cb3-106">멤버</span><span class="sxs-lookup"><span data-stu-id="49cb3-106">Member</span></span>|<span data-ttu-id="49cb3-107">설명</span><span class="sxs-lookup"><span data-stu-id="49cb3-107">Description</span></span>|  
|------------|-----------------|  
|`STEP_NORMAL`|<span data-ttu-id="49cb3-108">단계별 실행은 동일한 함수 내에서 정상적으로 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49cb3-108">Stepping completed normally, within the same function.</span></span>|  
|`STEP_RETURN`|<span data-ttu-id="49cb3-109">함수가 반환 된 후에도 정상적으로 계속 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49cb3-109">Stepping continued normally, after the function returned.</span></span>|  
|`STEP_CALL`|<span data-ttu-id="49cb3-110">새로 호출 된 함수가 시작 될 때 계속 해 서 단계별로 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="49cb3-110">Stepping continued normally, at the beginning of a newly called function.</span></span>|  
|`STEP_EXCEPTION_FILTER`|<span data-ttu-id="49cb3-111">예외가 생성 되었으며 컨트롤이 예외 필터로 전달 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="49cb3-111">An exception was generated and control was passed to an exception filter.</span></span>|  
|`STEP_EXCEPTION_HANDLER`|<span data-ttu-id="49cb3-112">예외가 생성 되었으며 컨트롤이 예외 처리기에 전달 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="49cb3-112">An exception was generated and control was passed to an exception handler.</span></span>|  
|`STEP_INTERCEPT`|<span data-ttu-id="49cb3-113">컨트롤이 인터셉터로 전달 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="49cb3-113">Control was passed to an interceptor.</span></span>|  
|`STEP_EXIT`|<span data-ttu-id="49cb3-114">단계가 완료 되기 전에 스레드가 종료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="49cb3-114">The thread exited before the step was completed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="49cb3-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="49cb3-115">Requirements</span></span>  
 <span data-ttu-id="49cb3-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="49cb3-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49cb3-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="49cb3-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="49cb3-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49cb3-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49cb3-119">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49cb3-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49cb3-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="49cb3-120">See also</span></span>

- [<span data-ttu-id="49cb3-121">StepComplete 메서드</span><span class="sxs-lookup"><span data-stu-id="49cb3-121">StepComplete Method</span></span>](icordebugmanagedcallback-stepcomplete-method.md)
- [<span data-ttu-id="49cb3-122">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="49cb3-122">Debugging Enumerations</span></span>](debugging-enumerations.md)
