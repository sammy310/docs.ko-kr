---
description: '다음에 대 한 자세한 정보: CorDebugIntercept 열거형'
title: CorDebugIntercept 열거형
ms.date: 03/30/2017
api_name:
- CorDebugIntercept
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugIntercept
helpviewer_keywords:
- CorDebugIntercept enumeration [.NET Framework debugging]
ms.assetid: 3d5b642e-7ef2-428b-a5ae-509c35ed461a
topic_type:
- apiref
ms.openlocfilehash: ddd17aff309396fdcda37c731ff907224ee17db2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661976"
---
# <a name="cordebugintercept-enumeration"></a><span data-ttu-id="90538-103">CorDebugIntercept 열거형</span><span class="sxs-lookup"><span data-stu-id="90538-103">CorDebugIntercept Enumeration</span></span>

<span data-ttu-id="90538-104">가로챌 수 있는(즉, 한 단계씩 실행할 수 있는) 코드 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="90538-104">Indicates the types of code that can be intercepted (that is, stepped into).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90538-105">구문</span><span class="sxs-lookup"><span data-stu-id="90538-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugIntercept {  
    INTERCEPT_NONE                = 0x0,  
    INTERCEPT_CLASS_INIT          = 0x01,  
    INTERCEPT_EXCEPTION_FILTER    = 0x02,  
    INTERCEPT_SECURITY            = 0x04,  
    INTERCEPT_CONTEXT_POLICY      = 0x08,  
    INTERCEPT_INTERCEPTION        = 0x10,  
    INTERCEPT_ALL                 = 0xffff  
} CorDebugIntercept;  
```  
  
## <a name="members"></a><span data-ttu-id="90538-106">구성원</span><span class="sxs-lookup"><span data-stu-id="90538-106">Members</span></span>  
  
|<span data-ttu-id="90538-107">멤버</span><span class="sxs-lookup"><span data-stu-id="90538-107">Member</span></span>|<span data-ttu-id="90538-108">설명</span><span class="sxs-lookup"><span data-stu-id="90538-108">Description</span></span>|  
|------------|-----------------|  
|`INTERCEPT_NONE`|<span data-ttu-id="90538-109">코드를 가로챌 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="90538-109">No code can be intercepted.</span></span>|  
|`INTERCEPT_CLASS_INIT`|<span data-ttu-id="90538-110">생성자를 가로챌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90538-110">A constructor can be intercepted.</span></span>|  
|`INTERCEPT_EXCEPTION_FILTER`|<span data-ttu-id="90538-111">예외 필터를 가로챌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90538-111">An exception filter can be intercepted.</span></span>|  
|`INTERCEPT_SECURITY`|<span data-ttu-id="90538-112">보안을 적용 하는 코드를 가로챌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90538-112">Code that enforces security can be intercepted.</span></span>|  
|`INTERCEPT_CONTEXT_POLICY`|<span data-ttu-id="90538-113">컨텍스트 정책을 가로챌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90538-113">A context policy can be intercepted.</span></span>|  
|`INTERCEPT_INTERCEPTION`|<span data-ttu-id="90538-114">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="90538-114">Not used.</span></span>|  
|`INTERCEPT_ALL`|<span data-ttu-id="90538-115">모든 코드를 가로챌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90538-115">All code can be intercepted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="90538-116">설명</span><span class="sxs-lookup"><span data-stu-id="90538-116">Remarks</span></span>  

 <span data-ttu-id="90538-117">[ICorDebugStepper:: SetInterceptMask](icordebugstepper-setinterceptmask-method.md) 메서드를 사용 하 여 가로챌 수 있는 코드의 형식을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="90538-117">Use the [ICorDebugStepper::SetInterceptMask](icordebugstepper-setinterceptmask-method.md) method to establish the types of code that can be intercepted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90538-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="90538-118">Requirements</span></span>  

 <span data-ttu-id="90538-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="90538-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90538-120">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="90538-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="90538-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90538-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90538-122">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90538-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90538-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="90538-123">See also</span></span>

- [<span data-ttu-id="90538-124">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="90538-124">Debugging Enumerations</span></span>](debugging-enumerations.md)
