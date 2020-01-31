---
title: ICorDebugStackWalk::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.Next Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::Next
helpviewer_keywords:
- ICorDebugStackWalk::Next method [.NET Framework debugging]
- Next method, ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 189c36be-028c-4fba-a002-5edfb8fcd07f
topic_type:
- apiref
ms.openlocfilehash: b76d17337408653d130ee0cb8594e759bdade37c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791862"
---
# <a name="icordebugstackwalknext-method"></a><span data-ttu-id="16aa1-102">ICorDebugStackWalk::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="16aa1-102">ICorDebugStackWalk::Next Method</span></span>
<span data-ttu-id="16aa1-103">[ICorDebugStackWalk](icordebugstackwalk-interface.md) 개체를 다음 프레임으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="16aa1-103">Moves the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object to the next frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16aa1-104">구문</span><span class="sxs-lookup"><span data-stu-id="16aa1-104">Syntax</span></span>  
  
```cpp  
HRESULT Next();  
```  
  
## <a name="return-value"></a><span data-ttu-id="16aa1-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="16aa1-105">Return Value</span></span>  
 <span data-ttu-id="16aa1-106">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="16aa1-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="16aa1-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="16aa1-107">HRESULT</span></span>|<span data-ttu-id="16aa1-108">설명</span><span class="sxs-lookup"><span data-stu-id="16aa1-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="16aa1-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="16aa1-109">S_OK</span></span>|<span data-ttu-id="16aa1-110">런타임이 다음 프레임으로 성공적으로 해제 되었습니다 (설명 참조).</span><span class="sxs-lookup"><span data-stu-id="16aa1-110">The runtime successfully unwound to the next frame (see Remarks).</span></span>|  
|<span data-ttu-id="16aa1-111">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="16aa1-111">E_FAIL</span></span>|<span data-ttu-id="16aa1-112">`ICorDebugStackWalk` 개체를 고급으로 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="16aa1-112">The `ICorDebugStackWalk` object could not be advanced.</span></span>|  
|<span data-ttu-id="16aa1-113">CORDBG_S_AT_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="16aa1-113">CORDBG_S_AT_END_OF_STACK</span></span>|<span data-ttu-id="16aa1-114">이 해제의 결과로 스택의 끝에 도달 했습니다.</span><span class="sxs-lookup"><span data-stu-id="16aa1-114">The end of the stack was reached as a result of this unwind.</span></span>|  
|<span data-ttu-id="16aa1-115">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="16aa1-115">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="16aa1-116">프레임 포인터가 이미 스택의 끝에 있습니다. 따라서 추가 프레임에는 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="16aa1-116">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="16aa1-117">예외</span><span class="sxs-lookup"><span data-stu-id="16aa1-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16aa1-118">주의</span><span class="sxs-lookup"><span data-stu-id="16aa1-118">Remarks</span></span>  
 <span data-ttu-id="16aa1-119">`Next` 메서드는 런타임에서 현재 프레임을 해제할 수 있는 경우에만 호출 하는 프레임으로 `ICorDebugStackWalk` 개체를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="16aa1-119">The `Next` method advances the `ICorDebugStackWalk` object to the calling frame only if the runtime can unwind the current frame.</span></span> <span data-ttu-id="16aa1-120">그렇지 않으면 개체는 런타임에서 해제할 수 있는 다음 프레임으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="16aa1-120">Otherwise, the object advances to the next frame that the runtime is able to unwind.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16aa1-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="16aa1-121">Requirements</span></span>  
 <span data-ttu-id="16aa1-122">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="16aa1-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16aa1-123">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="16aa1-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="16aa1-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="16aa1-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16aa1-125">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16aa1-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16aa1-126">참조</span><span class="sxs-lookup"><span data-stu-id="16aa1-126">See also</span></span>

- [<span data-ttu-id="16aa1-127">ICorDebugStackWalk 인터페이스</span><span class="sxs-lookup"><span data-stu-id="16aa1-127">ICorDebugStackWalk Interface</span></span>](icordebugstackwalk-interface.md)
- [<span data-ttu-id="16aa1-128">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="16aa1-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="16aa1-129">디버깅</span><span class="sxs-lookup"><span data-stu-id="16aa1-129">Debugging</span></span>](index.md)
