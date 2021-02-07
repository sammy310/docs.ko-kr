---
description: '자세히 알아보기: ICorDebugExceptionDebugEvent 인터페이스'
title: ICorDebugExceptionDebugEvent 인터페이스
ms.date: 03/30/2017
ms.assetid: f9ba60d8-b54d-417e-bb3e-fde4b41ca44c
ms.openlocfilehash: eacaa344763fb77faef5f66282809d741f017b37
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693423"
---
# <a name="icordebugexceptiondebugevent-interface"></a><span data-ttu-id="d74b4-103">ICorDebugExceptionDebugEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d74b4-103">ICorDebugExceptionDebugEvent Interface</span></span>

<span data-ttu-id="d74b4-104">[ICorDebugDebugEvent](icordebugdebugevent-interface.md) 인터페이스를 확장 하 여 예외 이벤트를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d74b4-104">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support exception events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d74b4-105">메서드</span><span class="sxs-lookup"><span data-stu-id="d74b4-105">Methods</span></span>  
  
|<span data-ttu-id="d74b4-106">메서드</span><span class="sxs-lookup"><span data-stu-id="d74b4-106">Method</span></span>|<span data-ttu-id="d74b4-107">설명</span><span class="sxs-lookup"><span data-stu-id="d74b4-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d74b4-108">GetFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="d74b4-108">GetFlags Method</span></span>](icordebugexceptiondebugevent-getflags-method.md)|<span data-ttu-id="d74b4-109">예외를 가로챌 수 있는지 여부를 나타내는 플래그를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d74b4-109">Gets a flag that indicates whether the exception is can be intercepted.</span></span>|  
|[<span data-ttu-id="d74b4-110">GetNativeIP 메서드</span><span class="sxs-lookup"><span data-stu-id="d74b4-110">GetNativeIP Method</span></span>](icordebugexceptiondebugevent-getnativeip-method.md)|<span data-ttu-id="d74b4-111">이 예외 디버그 이벤트에 대한 네이티브 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d74b4-111">Gets the native interface pointer for this exception debug event.</span></span>|  
|[<span data-ttu-id="d74b4-112">GetStackPointer 메서드</span><span class="sxs-lookup"><span data-stu-id="d74b4-112">GetStackPointer Method</span></span>](icordebugexceptiondebugevent-getstackpointer-method.md)|<span data-ttu-id="d74b4-113">이 예외 디버그 이벤트에 대한 스택 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d74b4-113">Gets the stack pointer for this exception debug event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d74b4-114">설명</span><span class="sxs-lookup"><span data-stu-id="d74b4-114">Remarks</span></span>  

 <span data-ttu-id="d74b4-115">`ICorDebugExceptionDebugEvent` 인터페이스는 다음 이벤트 유형을 통해 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="d74b4-115">The `ICorDebugExceptionDebugEvent` interface is implemented by the following event types:</span></span>  
  
- [<span data-ttu-id="d74b4-116">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="d74b4-116">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="d74b4-117">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="d74b4-117">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="d74b4-118">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="d74b4-118">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="d74b4-119">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="d74b4-119">MANAGED_EXCEPTION_UNHANDLED</span></span>](cordebugrecordformat-enumeration.md)  
  
> [!NOTE]
> <span data-ttu-id="d74b4-120">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d74b4-120">The interface is available with .NET Native only.</span></span> <span data-ttu-id="d74b4-121">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 `QueryInterface`를 호출하여 인터페이스 포인터를 검색하려고 하면 `E_NOINTERFACE`가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="d74b4-121">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d74b4-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d74b4-122">Requirements</span></span>  

 <span data-ttu-id="d74b4-123">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d74b4-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d74b4-124">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d74b4-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d74b4-125">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d74b4-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d74b4-126">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d74b4-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d74b4-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d74b4-127">See also</span></span>

- [<span data-ttu-id="d74b4-128">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d74b4-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="d74b4-129">디버깅</span><span class="sxs-lookup"><span data-stu-id="d74b4-129">Debugging</span></span>](index.md)
