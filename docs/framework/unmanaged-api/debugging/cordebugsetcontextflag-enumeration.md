---
title: CorDebugSetContextFlag 열거형
ms.date: 03/30/2017
api_name:
- CorDebugSetContextFlag
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugSetContextFlag
helpviewer_keywords:
- CorDebugSetContextFlag enumeration [.NET Framework debugging]
ms.assetid: b30280bb-fe75-44ed-8589-bcff081fae44
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e959ce7a77ad6ceb7f2fc848193cbd9fff028279
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739611"
---
# <a name="cordebugsetcontextflag-enumeration"></a><span data-ttu-id="91d42-102">CorDebugSetContextFlag 열거형</span><span class="sxs-lookup"><span data-stu-id="91d42-102">CorDebugSetContextFlag Enumeration</span></span>
<span data-ttu-id="91d42-103">컨텍스트가 스택의 활성(리프) 프레임에서 가져온 것인지 아니면 다른 프레임에서 해제하여 계산되었는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="91d42-103">Indicates whether the context is from the active (or leaf) frame on the stack or has been computed by unwinding from another frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91d42-104">구문</span><span class="sxs-lookup"><span data-stu-id="91d42-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugSetContextFlag  
{  
   SET_CONTEXT_FLAG_ACTIVE_FRAME = 1  
   SET_CONTEXT_FLAG_UNWIND_FRAME = 2  
}  CorDebugSetContextFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="91d42-105">멤버</span><span class="sxs-lookup"><span data-stu-id="91d42-105">Members</span></span>  
  
|<span data-ttu-id="91d42-106">멤버</span><span class="sxs-lookup"><span data-stu-id="91d42-106">Member</span></span>|<span data-ttu-id="91d42-107">Description</span><span class="sxs-lookup"><span data-stu-id="91d42-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="91d42-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span><span class="sxs-lookup"><span data-stu-id="91d42-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span></span>|<span data-ttu-id="91d42-109">컨텍스트는 스레드의 현재 컨텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="91d42-109">The context is the thread’s active context.</span></span>|  
|<span data-ttu-id="91d42-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span><span class="sxs-lookup"><span data-stu-id="91d42-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span></span>|<span data-ttu-id="91d42-111">컨텍스트는 다른 프레임에서 해제 하 여 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91d42-111">The context has been computed by unwinding from another frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91d42-112">설명</span><span class="sxs-lookup"><span data-stu-id="91d42-112">Remarks</span></span>  
 <span data-ttu-id="91d42-113">`CorDebugSetContextFlag` 사용 되는 값을 제공 합니다 [icordebugstackwalk:: Setcontext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="91d42-113">`CorDebugSetContextFlag` provides values that are used by the [ICorDebugStackWalk::SetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91d42-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="91d42-114">Requirements</span></span>  
 <span data-ttu-id="91d42-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="91d42-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91d42-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="91d42-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="91d42-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="91d42-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="91d42-118">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91d42-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91d42-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="91d42-119">See also</span></span>

- [<span data-ttu-id="91d42-120">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="91d42-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [<span data-ttu-id="91d42-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="91d42-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
