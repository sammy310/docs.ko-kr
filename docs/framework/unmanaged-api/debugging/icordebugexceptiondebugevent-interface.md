---
title: ICorDebugExceptionDebugEvent 인터페이스
ms.date: 03/30/2017
ms.assetid: f9ba60d8-b54d-417e-bb3e-fde4b41ca44c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2e2a147d46412eb4feb192070ff8420cab842a6c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995893"
---
# <a name="icordebugexceptiondebugevent-interface"></a><span data-ttu-id="02c54-102">ICorDebugExceptionDebugEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="02c54-102">ICorDebugExceptionDebugEvent Interface</span></span>
<span data-ttu-id="02c54-103">확장 된 [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) 예외 이벤트를 지 원하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="02c54-103">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support exception events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="02c54-104">메서드</span><span class="sxs-lookup"><span data-stu-id="02c54-104">Methods</span></span>  
  
|<span data-ttu-id="02c54-105">메서드</span><span class="sxs-lookup"><span data-stu-id="02c54-105">Method</span></span>|<span data-ttu-id="02c54-106">설명</span><span class="sxs-lookup"><span data-stu-id="02c54-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="02c54-107">GetFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="02c54-107">GetFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getflags-method.md)|<span data-ttu-id="02c54-108">예외를 가로챌 수 있는지 여부를 나타내는 플래그를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="02c54-108">Gets a flag that indicates whether the exception is can be intercepted.</span></span>|  
|[<span data-ttu-id="02c54-109">GetNativeIP 메서드</span><span class="sxs-lookup"><span data-stu-id="02c54-109">GetNativeIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getnativeip-method.md)|<span data-ttu-id="02c54-110">이 예외 디버그 이벤트에 대한 네이티브 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="02c54-110">Gets the native interface pointer for this exception debug event.</span></span>|  
|[<span data-ttu-id="02c54-111">GetStackPointer 메서드</span><span class="sxs-lookup"><span data-stu-id="02c54-111">GetStackPointer Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md)|<span data-ttu-id="02c54-112">이 예외 디버그 이벤트에 대한 스택 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="02c54-112">Gets the stack pointer for this exception debug event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02c54-113">설명</span><span class="sxs-lookup"><span data-stu-id="02c54-113">Remarks</span></span>  
 <span data-ttu-id="02c54-114">`ICorDebugExceptionDebugEvent` 인터페이스는 다음 이벤트 유형을 통해 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="02c54-114">The `ICorDebugExceptionDebugEvent` interface is implemented by the following event types:</span></span>  
  
- [<span data-ttu-id="02c54-115">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="02c54-115">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="02c54-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="02c54-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="02c54-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="02c54-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="02c54-118">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="02c54-118">MANAGED_EXCEPTION_UNHANDLED</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
> [!NOTE]
>  <span data-ttu-id="02c54-119">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02c54-119">The interface is available with .NET Native only.</span></span> <span data-ttu-id="02c54-120">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 `QueryInterface`를 호출하여 인터페이스 포인터를 검색하려고 하면 `E_NOINTERFACE`가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="02c54-120">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02c54-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="02c54-121">Requirements</span></span>  
 <span data-ttu-id="02c54-122">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="02c54-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02c54-123">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="02c54-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="02c54-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02c54-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02c54-125">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02c54-125">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02c54-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="02c54-126">See also</span></span>

- [<span data-ttu-id="02c54-127">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="02c54-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="02c54-128">디버깅</span><span class="sxs-lookup"><span data-stu-id="02c54-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
