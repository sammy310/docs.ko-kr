---
description: '다음에 대 한 자세한 정보: CorDebugSetContextFlag 열거형'
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
ms.openlocfilehash: 625f24e516ff462cf3d0e628dfff6c08793807ce
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801555"
---
# <a name="cordebugsetcontextflag-enumeration"></a><span data-ttu-id="2c1aa-103">CorDebugSetContextFlag 열거형</span><span class="sxs-lookup"><span data-stu-id="2c1aa-103">CorDebugSetContextFlag Enumeration</span></span>

<span data-ttu-id="2c1aa-104">컨텍스트가 스택의 활성(리프) 프레임에서 가져온 것인지 아니면 다른 프레임에서 해제하여 계산되었는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2c1aa-104">Indicates whether the context is from the active (or leaf) frame on the stack or has been computed by unwinding from another frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c1aa-105">구문</span><span class="sxs-lookup"><span data-stu-id="2c1aa-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugSetContextFlag  
{  
   SET_CONTEXT_FLAG_ACTIVE_FRAME = 1  
   SET_CONTEXT_FLAG_UNWIND_FRAME = 2  
}  CorDebugSetContextFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="2c1aa-106">구성원</span><span class="sxs-lookup"><span data-stu-id="2c1aa-106">Members</span></span>  
  
|<span data-ttu-id="2c1aa-107">멤버</span><span class="sxs-lookup"><span data-stu-id="2c1aa-107">Member</span></span>|<span data-ttu-id="2c1aa-108">설명</span><span class="sxs-lookup"><span data-stu-id="2c1aa-108">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="2c1aa-109">SET_CONTEXT_FLAG_ACTIVE_FRAME</span><span class="sxs-lookup"><span data-stu-id="2c1aa-109">SET_CONTEXT_FLAG_ACTIVE_FRAME</span></span>|<span data-ttu-id="2c1aa-110">컨텍스트는 스레드의 활성 컨텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="2c1aa-110">The context is the thread’s active context.</span></span>|  
|<span data-ttu-id="2c1aa-111">SET_CONTEXT_FLAG_UNWIND_FRAME</span><span class="sxs-lookup"><span data-stu-id="2c1aa-111">SET_CONTEXT_FLAG_UNWIND_FRAME</span></span>|<span data-ttu-id="2c1aa-112">다른 프레임에서 해제 하 여 컨텍스트를 계산 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2c1aa-112">The context has been computed by unwinding from another frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c1aa-113">설명</span><span class="sxs-lookup"><span data-stu-id="2c1aa-113">Remarks</span></span>  

 <span data-ttu-id="2c1aa-114">`CorDebugSetContextFlag`[ICorDebugStackWalk:: SetContext](icordebugstackwalk-setcontext-method.md) 메서드에서 사용 하는 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c1aa-114">`CorDebugSetContextFlag` provides values that are used by the [ICorDebugStackWalk::SetContext](icordebugstackwalk-setcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c1aa-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2c1aa-115">Requirements</span></span>  

 <span data-ttu-id="2c1aa-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2c1aa-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c1aa-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2c1aa-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2c1aa-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c1aa-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c1aa-119">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c1aa-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c1aa-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2c1aa-120">See also</span></span>

- [<span data-ttu-id="2c1aa-121">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="2c1aa-121">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="2c1aa-122">디버깅</span><span class="sxs-lookup"><span data-stu-id="2c1aa-122">Debugging</span></span>](index.md)
