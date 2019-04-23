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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 724db50285532c20132fbfd5262df26227db6742
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59130028"
---
# <a name="icordebugstackwalknext-method"></a><span data-ttu-id="43d79-102">ICorDebugStackWalk::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="43d79-102">ICorDebugStackWalk::Next Method</span></span>
<span data-ttu-id="43d79-103">이동 합니다 [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) 다음 프레임으로 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="43d79-103">Moves the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object to the next frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43d79-104">구문</span><span class="sxs-lookup"><span data-stu-id="43d79-104">Syntax</span></span>  
  
```  
HRESULT Next();  
```  
  
## <a name="return-value"></a><span data-ttu-id="43d79-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="43d79-105">Return Value</span></span>  
 <span data-ttu-id="43d79-106">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="43d79-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="43d79-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="43d79-107">HRESULT</span></span>|<span data-ttu-id="43d79-108">설명</span><span class="sxs-lookup"><span data-stu-id="43d79-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="43d79-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="43d79-109">S_OK</span></span>|<span data-ttu-id="43d79-110">런타임은 다음 프레임으로 성공적으로 해제 되었습니다 (설명 참조).</span><span class="sxs-lookup"><span data-stu-id="43d79-110">The runtime successfully unwound to the next frame (see Remarks).</span></span>|  
|<span data-ttu-id="43d79-111">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="43d79-111">E_FAIL</span></span>|<span data-ttu-id="43d79-112">`ICorDebugStackWalk` 개체를 이동할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="43d79-112">The `ICorDebugStackWalk` object could not be advanced.</span></span>|  
|<span data-ttu-id="43d79-113">CORDBG_S_AT_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="43d79-113">CORDBG_S_AT_END_OF_STACK</span></span>|<span data-ttu-id="43d79-114">이 해제의 결과로 스택의 끝에 도달 했습니다.</span><span class="sxs-lookup"><span data-stu-id="43d79-114">The end of the stack was reached as a result of this unwind.</span></span>|  
|<span data-ttu-id="43d79-115">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="43d79-115">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="43d79-116">프레임 포인터 끝 스택;에 이미 따라서 추가 프레임 없음 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43d79-116">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="43d79-117">예외</span><span class="sxs-lookup"><span data-stu-id="43d79-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43d79-118">설명</span><span class="sxs-lookup"><span data-stu-id="43d79-118">Remarks</span></span>  
 <span data-ttu-id="43d79-119">합니다 `Next` 메서드 발전을 `ICorDebugStackWalk` 런타임은 현재 프레임을 해제할 수 있는 경우에 호출 프레임으로 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="43d79-119">The `Next` method advances the `ICorDebugStackWalk` object to the calling frame only if the runtime can unwind the current frame.</span></span> <span data-ttu-id="43d79-120">그렇지 않으면 개체 런타임에서 해제 수 있는 다음 프레임으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="43d79-120">Otherwise, the object advances to the next frame that the runtime is able to unwind.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43d79-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="43d79-121">Requirements</span></span>  
 <span data-ttu-id="43d79-122">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="43d79-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43d79-123">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="43d79-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43d79-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43d79-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43d79-125">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43d79-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43d79-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="43d79-126">See also</span></span>

- [<span data-ttu-id="43d79-127">ICorDebugStackWalk 인터페이스</span><span class="sxs-lookup"><span data-stu-id="43d79-127">ICorDebugStackWalk Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)
- [<span data-ttu-id="43d79-128">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="43d79-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="43d79-129">디버깅</span><span class="sxs-lookup"><span data-stu-id="43d79-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
