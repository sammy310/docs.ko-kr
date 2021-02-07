---
description: '자세히 알아보기: ICorDebugStackWalk:: Next 메서드'
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
ms.openlocfilehash: 27a48ca40f6b43cae32511b71b73e68d88eb60c0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717760"
---
# <a name="icordebugstackwalknext-method"></a><span data-ttu-id="f6b99-103">ICorDebugStackWalk::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="f6b99-103">ICorDebugStackWalk::Next Method</span></span>

<span data-ttu-id="f6b99-104">[ICorDebugStackWalk](icordebugstackwalk-interface.md) 개체를 다음 프레임으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6b99-104">Moves the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object to the next frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6b99-105">구문</span><span class="sxs-lookup"><span data-stu-id="f6b99-105">Syntax</span></span>  
  
```cpp  
HRESULT Next();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f6b99-106">Return Value</span><span class="sxs-lookup"><span data-stu-id="f6b99-106">Return Value</span></span>  

 <span data-ttu-id="f6b99-107">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f6b99-107">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="f6b99-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f6b99-108">HRESULT</span></span>|<span data-ttu-id="f6b99-109">설명</span><span class="sxs-lookup"><span data-stu-id="f6b99-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f6b99-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f6b99-110">S_OK</span></span>|<span data-ttu-id="f6b99-111">런타임이 다음 프레임으로 성공적으로 해제 되었습니다 (설명 참조).</span><span class="sxs-lookup"><span data-stu-id="f6b99-111">The runtime successfully unwound to the next frame (see Remarks).</span></span>|  
|<span data-ttu-id="f6b99-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f6b99-112">E_FAIL</span></span>|<span data-ttu-id="f6b99-113">`ICorDebugStackWalk`개체를 고급으로 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f6b99-113">The `ICorDebugStackWalk` object could not be advanced.</span></span>|  
|<span data-ttu-id="f6b99-114">CORDBG_S_AT_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="f6b99-114">CORDBG_S_AT_END_OF_STACK</span></span>|<span data-ttu-id="f6b99-115">이 해제의 결과로 스택의 끝에 도달 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f6b99-115">The end of the stack was reached as a result of this unwind.</span></span>|  
|<span data-ttu-id="f6b99-116">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="f6b99-116">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="f6b99-117">프레임 포인터가 이미 스택의 끝에 있습니다. 따라서 추가 프레임에는 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f6b99-117">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="f6b99-118">예외</span><span class="sxs-lookup"><span data-stu-id="f6b99-118">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6b99-119">설명</span><span class="sxs-lookup"><span data-stu-id="f6b99-119">Remarks</span></span>  

 <span data-ttu-id="f6b99-120">`Next`메서드는 `ICorDebugStackWalk` 런타임에서 현재 프레임을 해제할 수 있는 경우에만 개체를 호출 프레임으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6b99-120">The `Next` method advances the `ICorDebugStackWalk` object to the calling frame only if the runtime can unwind the current frame.</span></span> <span data-ttu-id="f6b99-121">그렇지 않으면 개체는 런타임에서 해제할 수 있는 다음 프레임으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6b99-121">Otherwise, the object advances to the next frame that the runtime is able to unwind.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6b99-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f6b99-122">Requirements</span></span>  

 <span data-ttu-id="f6b99-123">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f6b99-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6b99-124">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f6b99-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f6b99-125">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6b99-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6b99-126">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6b99-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6b99-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f6b99-127">See also</span></span>

- [<span data-ttu-id="f6b99-128">ICorDebugStackWalk 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f6b99-128">ICorDebugStackWalk Interface</span></span>](icordebugstackwalk-interface.md)
- [<span data-ttu-id="f6b99-129">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f6b99-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="f6b99-130">디버깅</span><span class="sxs-lookup"><span data-stu-id="f6b99-130">Debugging</span></span>](index.md)
