---
title: ICorDebugNativeFrame 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame
helpviewer_keywords:
- ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 04819c58-7246-4b32-befb-680cf1dbc436
topic_type:
- apiref
ms.openlocfilehash: 043dc0fdd5218d7bc6b80428d1eb891b3f01ee8c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695545"
---
# <a name="icordebugnativeframe-interface"></a><span data-ttu-id="595a4-102">ICorDebugNativeFrame 인터페이스</span><span class="sxs-lookup"><span data-stu-id="595a4-102">ICorDebugNativeFrame Interface</span></span>

<span data-ttu-id="595a4-103">네이티브 프레임에 사용 되는 ICorDebugFrame의 특수화 된 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="595a4-103">A specialized implementation of ICorDebugFrame used for native frames.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="595a4-104">메서드</span><span class="sxs-lookup"><span data-stu-id="595a4-104">Methods</span></span>  
  
|<span data-ttu-id="595a4-105">메서드</span><span class="sxs-lookup"><span data-stu-id="595a4-105">Method</span></span>|<span data-ttu-id="595a4-106">설명</span><span class="sxs-lookup"><span data-stu-id="595a4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="595a4-107">CanSetIP 메서드</span><span class="sxs-lookup"><span data-stu-id="595a4-107">CanSetIP Method</span></span>](icordebugnativeframe-cansetip-method.md)|<span data-ttu-id="595a4-108">네이티브 코드에서 지정 된 오프셋 위치에 대 한 명령 포인터를 설정 하는 것이 안전한 지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="595a4-108">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location in native code.</span></span>|  
|[<span data-ttu-id="595a4-109">GetIP 메서드</span><span class="sxs-lookup"><span data-stu-id="595a4-109">GetIP Method</span></span>](icordebugnativeframe-getip-method.md)|<span data-ttu-id="595a4-110">네이티브 코드에 대 한 스택 프레임의 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="595a4-110">Gets the stack frame's offset into native code.</span></span>|  
|[<span data-ttu-id="595a4-111">GetLocalDoubleRegisterValue 메서드</span><span class="sxs-lookup"><span data-stu-id="595a4-111">GetLocalDoubleRegisterValue Method</span></span>](icordebugnativeframe-getlocaldoubleregistervalue-method.md)|<span data-ttu-id="595a4-112">네이티브 프레임의 두 메모리 레지스터에 저장 된 인수나 지역 변수의 값을 나타내는 ICorDebugValue에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="595a4-112">Gets a pointer to an ICorDebugValue that represents the value of an argument or local variable stored in two memory registers of a native frame.</span></span>|  
|[<span data-ttu-id="595a4-113">GetLocalMemoryRegisterValue 메서드</span><span class="sxs-lookup"><span data-stu-id="595a4-113">GetLocalMemoryRegisterValue Method</span></span>](icordebugnativeframe-getlocalmemoryregistervalue-method.md)|<span data-ttu-id="595a4-114">`ICorDebugValue`하위 비트가 지정 된 레지스터에 저장 되 고 상위 비트가 지정 된 메모리 주소에 저장 되는 지역 변수의 값을 나타내는에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="595a4-114">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the low bits are stored in the specified register and the high bits are stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="595a4-115">GetLocalMemoryValue 메서드</span><span class="sxs-lookup"><span data-stu-id="595a4-115">GetLocalMemoryValue Method</span></span>](icordebugnativeframe-getlocalmemoryvalue-method.md)|<span data-ttu-id="595a4-116">`ICorDebugValue`지정 된 메모리 주소에 저장 된 지역 변수의 값을 나타내는에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="595a4-116">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="595a4-117">GetLocalRegisterMemoryValue 메서드</span><span class="sxs-lookup"><span data-stu-id="595a4-117">GetLocalRegisterMemoryValue Method</span></span>](icordebugnativeframe-getlocalregistermemoryvalue-method.md)|<span data-ttu-id="595a4-118">`ICorDebugValue`상위 비트가 지정 된 레지스터에 저장 되 고 하위 비트가 지정 된 메모리 주소에 저장 되는 지역 변수의 값을 나타내는에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="595a4-118">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the high bits are stored in the specified register and the low bits are stored at the specified memory address</span></span>|  
|[<span data-ttu-id="595a4-119">GetLocalRegisterValue 메서드</span><span class="sxs-lookup"><span data-stu-id="595a4-119">GetLocalRegisterValue Method</span></span>](icordebugnativeframe-getlocalregistervalue-method.md)|<span data-ttu-id="595a4-120">`ICorDebugValue`지정 된 네이티브 레지스터에 저장 된 인수 또는 지역 변수의 값을 나타내는에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="595a4-120">Gets a pointer to an `ICorDebugValue` that represents the value of an argument or a local variable stored in the specified native register.</span></span>|  
|[<span data-ttu-id="595a4-121">GetRegisterSet 메서드</span><span class="sxs-lookup"><span data-stu-id="595a4-121">GetRegisterSet Method</span></span>](icordebugnativeframe-getregisterset-method.md)|<span data-ttu-id="595a4-122">이에 대 한 레지스터 집합을 나타내는 [ICorDebugRegisterSet](icordebugregisterset-interface.md) 에 대 한 포인터를 가져옵니다 `ICorDebugNativeFrame` .</span><span class="sxs-lookup"><span data-stu-id="595a4-122">Gets a pointer to an [ICorDebugRegisterSet](icordebugregisterset-interface.md) that represents the register set for this `ICorDebugNativeFrame`.</span></span>|  
|[<span data-ttu-id="595a4-123">SetIP 메서드</span><span class="sxs-lookup"><span data-stu-id="595a4-123">SetIP Method</span></span>](icordebugnativeframe-setip-method.md)|<span data-ttu-id="595a4-124">네이티브 코드에서 지정 된 오프셋 위치에 대 한 명령 포인터를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a4-124">Sets the instruction pointer to the specified offset location in native code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="595a4-125">설명</span><span class="sxs-lookup"><span data-stu-id="595a4-125">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="595a4-126">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="595a4-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="595a4-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="595a4-127">Requirements</span></span>  

 <span data-ttu-id="595a4-128">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="595a4-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="595a4-129">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="595a4-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="595a4-130">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="595a4-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="595a4-131">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="595a4-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="595a4-132">참조</span><span class="sxs-lookup"><span data-stu-id="595a4-132">See also</span></span>

- [<span data-ttu-id="595a4-133">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="595a4-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
