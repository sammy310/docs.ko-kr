---
description: '자세히 알아보기: ICorDebugFrame 인터페이스'
title: ICorDebugFrame 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame
helpviewer_keywords:
- ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 0c48f764-3c64-4602-b2f4-4ffc60eb2c65
topic_type:
- apiref
ms.openlocfilehash: d0fd629672d535f89fe78c178032937443d9dfbd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692851"
---
# <a name="icordebugframe-interface"></a><span data-ttu-id="c9f10-103">ICorDebugFrame 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c9f10-103">ICorDebugFrame Interface</span></span>

<span data-ttu-id="c9f10-104">현재 스택의 프레임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c9f10-104">Represents a frame on the current stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c9f10-105">메서드</span><span class="sxs-lookup"><span data-stu-id="c9f10-105">Methods</span></span>  
  
|<span data-ttu-id="c9f10-106">메서드</span><span class="sxs-lookup"><span data-stu-id="c9f10-106">Method</span></span>|<span data-ttu-id="c9f10-107">설명</span><span class="sxs-lookup"><span data-stu-id="c9f10-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c9f10-108">CreateStepper 메서드</span><span class="sxs-lookup"><span data-stu-id="c9f10-108">CreateStepper Method</span></span>](icordebugframe-createstepper-method.md)|<span data-ttu-id="c9f10-109">이에 상대적인 단계별 작업을 수행할 ICorDebugStepper를 가져옵니다 `ICorDebugFrame` .</span><span class="sxs-lookup"><span data-stu-id="c9f10-109">Gets an ICorDebugStepper to perform stepping operations relative to this `ICorDebugFrame`.</span></span>|  
|[<span data-ttu-id="c9f10-110">GetCallee 메서드</span><span class="sxs-lookup"><span data-stu-id="c9f10-110">GetCallee Method</span></span>](icordebugframe-getcallee-method.md)|<span data-ttu-id="c9f10-111">`ICorDebugFrame`이 프레임이 호출 하는 현재 체인의에 대 한 포인터를 가져오거나, 체인이 가장 안쪽 프레임 인 경우 null을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9f10-111">Gets a pointer to the `ICorDebugFrame` in the current chain that this frame called, or returns null if this is the innermost frame in the chain.</span></span>|  
|[<span data-ttu-id="c9f10-112">GetCaller 메서드</span><span class="sxs-lookup"><span data-stu-id="c9f10-112">GetCaller Method</span></span>](icordebugframe-getcaller-method.md)|<span data-ttu-id="c9f10-113">`ICorDebugFrame`현재 체인에서이 프레임을 호출한에 대 한 포인터를 가져오거나, 체인에서 가장 바깥쪽 프레임 인 경우 null을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9f10-113">Gets a pointer to the `ICorDebugFrame` in the current chain that called this frame, or returns null if this is the outermost frame in the chain.</span></span>|  
|[<span data-ttu-id="c9f10-114">GetChain 메서드</span><span class="sxs-lookup"><span data-stu-id="c9f10-114">GetChain Method</span></span>](icordebugframe-getchain-method.md)|<span data-ttu-id="c9f10-115">이가 포함 된 ICorDebugChain에 대 한 포인터를 가져옵니다 `ICorDebugFrame` .</span><span class="sxs-lookup"><span data-stu-id="c9f10-115">Gets a pointer to the ICorDebugChain this `ICorDebugFrame` is a part of.</span></span>|  
|[<span data-ttu-id="c9f10-116">GetCode 메서드</span><span class="sxs-lookup"><span data-stu-id="c9f10-116">GetCode Method</span></span>](icordebugframe-getcode-method.md)|<span data-ttu-id="c9f10-117">이 스택 프레임과 연결 된 ICorDebugCode에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c9f10-117">Gets a pointer to the ICorDebugCode associated with this stack frame.</span></span>|  
|[<span data-ttu-id="c9f10-118">GetFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="c9f10-118">GetFunction Method</span></span>](icordebugframe-getfunction-method.md)|<span data-ttu-id="c9f10-119">이 스택 프레임과 연결 된 코드를 포함 하는 ICorDebugFunction에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c9f10-119">Gets a pointer to the ICorDebugFunction that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="c9f10-120">GetFunctionToken 메서드</span><span class="sxs-lookup"><span data-stu-id="c9f10-120">GetFunctionToken Method</span></span>](icordebugframe-getfunctiontoken-method.md)|<span data-ttu-id="c9f10-121">이 스택 프레임과 연결 된 코드를 포함 하는 함수에 대 한 메타 데이터 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c9f10-121">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="c9f10-122">GetStackRange 메서드</span><span class="sxs-lookup"><span data-stu-id="c9f10-122">GetStackRange Method</span></span>](icordebugframe-getstackrange-method.md)|<span data-ttu-id="c9f10-123">이가 나타내는 스택 프레임의 절대 주소 범위를 가져옵니다 `ICorDebugFrame` .</span><span class="sxs-lookup"><span data-stu-id="c9f10-123">Gets the absolute address range of the stack frame represented by this `ICorDebugFrame`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9f10-124">설명</span><span class="sxs-lookup"><span data-stu-id="c9f10-124">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c9f10-125">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9f10-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9f10-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c9f10-126">Requirements</span></span>  

 <span data-ttu-id="c9f10-127">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c9f10-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9f10-128">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c9f10-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c9f10-129">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9f10-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9f10-130">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9f10-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9f10-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c9f10-131">See also</span></span>

- [<span data-ttu-id="c9f10-132">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c9f10-132">Debugging Interfaces</span></span>](debugging-interfaces.md)
