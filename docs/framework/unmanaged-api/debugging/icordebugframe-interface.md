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
ms.openlocfilehash: ba138e79e0d6fb6f9c5e9c3efe3466f3c88cccae
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782617"
---
# <a name="icordebugframe-interface"></a><span data-ttu-id="4e6be-102">ICorDebugFrame 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4e6be-102">ICorDebugFrame Interface</span></span>

<span data-ttu-id="4e6be-103">현재 스택의 프레임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4e6be-103">Represents a frame on the current stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4e6be-104">메서드</span><span class="sxs-lookup"><span data-stu-id="4e6be-104">Methods</span></span>  
  
|<span data-ttu-id="4e6be-105">메서드</span><span class="sxs-lookup"><span data-stu-id="4e6be-105">Method</span></span>|<span data-ttu-id="4e6be-106">설명</span><span class="sxs-lookup"><span data-stu-id="4e6be-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4e6be-107">CreateStepper 메서드</span><span class="sxs-lookup"><span data-stu-id="4e6be-107">CreateStepper Method</span></span>](icordebugframe-createstepper-method.md)|<span data-ttu-id="4e6be-108">이 `ICorDebugFrame`에 상대적인 단계별 작업을 수행할 ICorDebugStepper를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4e6be-108">Gets an ICorDebugStepper to perform stepping operations relative to this `ICorDebugFrame`.</span></span>|  
|[<span data-ttu-id="4e6be-109">GetCallee 메서드</span><span class="sxs-lookup"><span data-stu-id="4e6be-109">GetCallee Method</span></span>](icordebugframe-getcallee-method.md)|<span data-ttu-id="4e6be-110">이 프레임에서 호출한 현재 체인의 `ICorDebugFrame`에 대 한 포인터를 가져오거나, 체인에서 가장 안쪽 프레임 인 경우 null을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e6be-110">Gets a pointer to the `ICorDebugFrame` in the current chain that this frame called, or returns null if this is the innermost frame in the chain.</span></span>|  
|[<span data-ttu-id="4e6be-111">GetCaller 메서드</span><span class="sxs-lookup"><span data-stu-id="4e6be-111">GetCaller Method</span></span>](icordebugframe-getcaller-method.md)|<span data-ttu-id="4e6be-112">이 프레임을 호출한 현재 체인의 `ICorDebugFrame`에 대 한 포인터를 가져오거나, 체인에서 가장 바깥쪽 프레임 인 경우 null을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e6be-112">Gets a pointer to the `ICorDebugFrame` in the current chain that called this frame, or returns null if this is the outermost frame in the chain.</span></span>|  
|[<span data-ttu-id="4e6be-113">GetChain 메서드</span><span class="sxs-lookup"><span data-stu-id="4e6be-113">GetChain Method</span></span>](icordebugframe-getchain-method.md)|<span data-ttu-id="4e6be-114">이 `ICorDebugFrame` 포함 된 ICorDebugChain에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4e6be-114">Gets a pointer to the ICorDebugChain this `ICorDebugFrame` is a part of.</span></span>|  
|[<span data-ttu-id="4e6be-115">GetCode 메서드</span><span class="sxs-lookup"><span data-stu-id="4e6be-115">GetCode Method</span></span>](icordebugframe-getcode-method.md)|<span data-ttu-id="4e6be-116">이 스택 프레임과 연결 된 ICorDebugCode에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4e6be-116">Gets a pointer to the ICorDebugCode associated with this stack frame.</span></span>|  
|[<span data-ttu-id="4e6be-117">GetFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="4e6be-117">GetFunction Method</span></span>](icordebugframe-getfunction-method.md)|<span data-ttu-id="4e6be-118">이 스택 프레임과 연결 된 코드를 포함 하는 ICorDebugFunction에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4e6be-118">Gets a pointer to the ICorDebugFunction that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="4e6be-119">GetFunctionToken 메서드</span><span class="sxs-lookup"><span data-stu-id="4e6be-119">GetFunctionToken Method</span></span>](icordebugframe-getfunctiontoken-method.md)|<span data-ttu-id="4e6be-120">이 스택 프레임과 연결 된 코드를 포함 하는 함수에 대 한 메타 데이터 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4e6be-120">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="4e6be-121">GetStackRange 메서드</span><span class="sxs-lookup"><span data-stu-id="4e6be-121">GetStackRange Method</span></span>](icordebugframe-getstackrange-method.md)|<span data-ttu-id="4e6be-122">이 `ICorDebugFrame`표시 하는 스택 프레임의 절대 주소 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4e6be-122">Gets the absolute address range of the stack frame represented by this `ICorDebugFrame`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e6be-123">주의</span><span class="sxs-lookup"><span data-stu-id="4e6be-123">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4e6be-124">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e6be-124">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e6be-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4e6be-125">Requirements</span></span>  
 <span data-ttu-id="4e6be-126">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e6be-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e6be-127">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4e6be-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4e6be-128">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e6be-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e6be-129">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e6be-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e6be-130">참조</span><span class="sxs-lookup"><span data-stu-id="4e6be-130">See also</span></span>

- [<span data-ttu-id="4e6be-131">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4e6be-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
