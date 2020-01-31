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
ms.openlocfilehash: a443332e4f2b0351e99754fae610af39268bb105
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789264"
---
# <a name="cordebugsetcontextflag-enumeration"></a><span data-ttu-id="a4a73-102">CorDebugSetContextFlag 열거형</span><span class="sxs-lookup"><span data-stu-id="a4a73-102">CorDebugSetContextFlag Enumeration</span></span>
<span data-ttu-id="a4a73-103">컨텍스트가 스택의 활성(리프) 프레임에서 가져온 것인지 아니면 다른 프레임에서 해제하여 계산되었는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a4a73-103">Indicates whether the context is from the active (or leaf) frame on the stack or has been computed by unwinding from another frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4a73-104">구문</span><span class="sxs-lookup"><span data-stu-id="a4a73-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugSetContextFlag  
{  
   SET_CONTEXT_FLAG_ACTIVE_FRAME = 1  
   SET_CONTEXT_FLAG_UNWIND_FRAME = 2  
}  CorDebugSetContextFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="a4a73-105">Members</span><span class="sxs-lookup"><span data-stu-id="a4a73-105">Members</span></span>  
  
|<span data-ttu-id="a4a73-106">Member</span><span class="sxs-lookup"><span data-stu-id="a4a73-106">Member</span></span>|<span data-ttu-id="a4a73-107">설명</span><span class="sxs-lookup"><span data-stu-id="a4a73-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="a4a73-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span><span class="sxs-lookup"><span data-stu-id="a4a73-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span></span>|<span data-ttu-id="a4a73-109">컨텍스트는 스레드의 활성 컨텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="a4a73-109">The context is the thread’s active context.</span></span>|  
|<span data-ttu-id="a4a73-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span><span class="sxs-lookup"><span data-stu-id="a4a73-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span></span>|<span data-ttu-id="a4a73-111">다른 프레임에서 해제 하 여 컨텍스트를 계산 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a4a73-111">The context has been computed by unwinding from another frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4a73-112">주의</span><span class="sxs-lookup"><span data-stu-id="a4a73-112">Remarks</span></span>  
 <span data-ttu-id="a4a73-113">`CorDebugSetContextFlag` [ICorDebugStackWalk:: SetContext](icordebugstackwalk-setcontext-method.md) 메서드에서 사용 하는 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4a73-113">`CorDebugSetContextFlag` provides values that are used by the [ICorDebugStackWalk::SetContext](icordebugstackwalk-setcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4a73-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a4a73-114">Requirements</span></span>  
 <span data-ttu-id="a4a73-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a4a73-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4a73-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a4a73-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a4a73-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4a73-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a4a73-118">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4a73-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4a73-119">참조</span><span class="sxs-lookup"><span data-stu-id="a4a73-119">See also</span></span>

- [<span data-ttu-id="a4a73-120">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="a4a73-120">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="a4a73-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="a4a73-121">Debugging</span></span>](index.md)
