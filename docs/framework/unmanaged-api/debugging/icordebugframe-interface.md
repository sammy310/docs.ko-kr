---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d4744ea67d0ce0d9ad2b13c45bdef65f884ef925
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937000"
---
# <a name="icordebugframe-interface"></a><span data-ttu-id="d14cd-102">ICorDebugFrame 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d14cd-102">ICorDebugFrame Interface</span></span>

<span data-ttu-id="d14cd-103">현재 스택의 프레임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d14cd-103">Represents a frame on the current stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d14cd-104">메서드</span><span class="sxs-lookup"><span data-stu-id="d14cd-104">Methods</span></span>  
  
|<span data-ttu-id="d14cd-105">메서드</span><span class="sxs-lookup"><span data-stu-id="d14cd-105">Method</span></span>|<span data-ttu-id="d14cd-106">Description</span><span class="sxs-lookup"><span data-stu-id="d14cd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d14cd-107">CreateStepper 메서드</span><span class="sxs-lookup"><span data-stu-id="d14cd-107">CreateStepper Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-createstepper-method.md)|<span data-ttu-id="d14cd-108">이 `ICorDebugFrame`에 상대적인 단계별 작업을 수행할 ICorDebugStepper를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d14cd-108">Gets an ICorDebugStepper to perform stepping operations relative to this `ICorDebugFrame`.</span></span>|  
|[<span data-ttu-id="d14cd-109">GetCallee 메서드</span><span class="sxs-lookup"><span data-stu-id="d14cd-109">GetCallee Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcallee-method.md)|<span data-ttu-id="d14cd-110">이 프레임이 호출 하는 `ICorDebugFrame` 현재 체인의에 대 한 포인터를 가져오거나, 체인이 가장 안쪽 프레임 인 경우 null을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d14cd-110">Gets a pointer to the `ICorDebugFrame` in the current chain that this frame called, or returns null if this is the innermost frame in the chain.</span></span>|  
|[<span data-ttu-id="d14cd-111">GetCaller 메서드</span><span class="sxs-lookup"><span data-stu-id="d14cd-111">GetCaller Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcaller-method.md)|<span data-ttu-id="d14cd-112">현재 체인 `ICorDebugFrame` 에서이 프레임을 호출한에 대 한 포인터를 가져오거나, 체인에서 가장 바깥쪽 프레임 인 경우 null을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d14cd-112">Gets a pointer to the `ICorDebugFrame` in the current chain that called this frame, or returns null if this is the outermost frame in the chain.</span></span>|  
|[<span data-ttu-id="d14cd-113">GetChain 메서드</span><span class="sxs-lookup"><span data-stu-id="d14cd-113">GetChain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getchain-method.md)|<span data-ttu-id="d14cd-114">이 `ICorDebugFrame` 가 포함 된 ICorDebugChain에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d14cd-114">Gets a pointer to the ICorDebugChain this `ICorDebugFrame` is a part of.</span></span>|  
|[<span data-ttu-id="d14cd-115">GetCode 메서드</span><span class="sxs-lookup"><span data-stu-id="d14cd-115">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)|<span data-ttu-id="d14cd-116">이 스택 프레임과 연결 된 ICorDebugCode에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d14cd-116">Gets a pointer to the ICorDebugCode associated with this stack frame.</span></span>|  
|[<span data-ttu-id="d14cd-117">GetFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="d14cd-117">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunction-method.md)|<span data-ttu-id="d14cd-118">이 스택 프레임과 연결 된 코드를 포함 하는 ICorDebugFunction에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d14cd-118">Gets a pointer to the ICorDebugFunction that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="d14cd-119">GetFunctionToken 메서드</span><span class="sxs-lookup"><span data-stu-id="d14cd-119">GetFunctionToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunctiontoken-method.md)|<span data-ttu-id="d14cd-120">이 스택 프레임과 연결 된 코드를 포함 하는 함수에 대 한 메타 데이터 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d14cd-120">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="d14cd-121">GetStackRange 메서드</span><span class="sxs-lookup"><span data-stu-id="d14cd-121">GetStackRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getstackrange-method.md)|<span data-ttu-id="d14cd-122">이 `ICorDebugFrame`가 나타내는 스택 프레임의 절대 주소 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d14cd-122">Gets the absolute address range of the stack frame represented by this `ICorDebugFrame`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d14cd-123">설명</span><span class="sxs-lookup"><span data-stu-id="d14cd-123">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d14cd-124">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d14cd-124">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d14cd-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d14cd-125">Requirements</span></span>  
 <span data-ttu-id="d14cd-126">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d14cd-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d14cd-127">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d14cd-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d14cd-128">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d14cd-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d14cd-129">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d14cd-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d14cd-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="d14cd-130">See also</span></span>

- [<span data-ttu-id="d14cd-131">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d14cd-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
