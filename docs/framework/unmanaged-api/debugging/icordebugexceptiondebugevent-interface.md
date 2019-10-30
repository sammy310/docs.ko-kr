---
title: ICorDebugExceptionDebugEvent 인터페이스
ms.date: 03/30/2017
ms.assetid: f9ba60d8-b54d-417e-bb3e-fde4b41ca44c
ms.openlocfilehash: 985edaa14510b7ca03399ae17cf1d89f28fd04c3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084646"
---
# <a name="icordebugexceptiondebugevent-interface"></a><span data-ttu-id="0a273-102">ICorDebugExceptionDebugEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0a273-102">ICorDebugExceptionDebugEvent Interface</span></span>
<span data-ttu-id="0a273-103">[ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) 인터페이스를 확장 하 여 예외 이벤트를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a273-103">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support exception events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0a273-104">메서드</span><span class="sxs-lookup"><span data-stu-id="0a273-104">Methods</span></span>  
  
|<span data-ttu-id="0a273-105">메서드</span><span class="sxs-lookup"><span data-stu-id="0a273-105">Method</span></span>|<span data-ttu-id="0a273-106">설명</span><span class="sxs-lookup"><span data-stu-id="0a273-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0a273-107">GetFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="0a273-107">GetFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getflags-method.md)|<span data-ttu-id="0a273-108">예외를 가로챌 수 있는지 여부를 나타내는 플래그를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0a273-108">Gets a flag that indicates whether the exception is can be intercepted.</span></span>|  
|[<span data-ttu-id="0a273-109">GetNativeIP 메서드</span><span class="sxs-lookup"><span data-stu-id="0a273-109">GetNativeIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getnativeip-method.md)|<span data-ttu-id="0a273-110">이 예외 디버그 이벤트에 대한 네이티브 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0a273-110">Gets the native interface pointer for this exception debug event.</span></span>|  
|[<span data-ttu-id="0a273-111">GetStackPointer 메서드</span><span class="sxs-lookup"><span data-stu-id="0a273-111">GetStackPointer Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md)|<span data-ttu-id="0a273-112">이 예외 디버그 이벤트에 대한 스택 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0a273-112">Gets the stack pointer for this exception debug event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0a273-113">주의</span><span class="sxs-lookup"><span data-stu-id="0a273-113">Remarks</span></span>  
 <span data-ttu-id="0a273-114">`ICorDebugExceptionDebugEvent` 인터페이스는 다음 이벤트 유형을 통해 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a273-114">The `ICorDebugExceptionDebugEvent` interface is implemented by the following event types:</span></span>  
  
- [<span data-ttu-id="0a273-115">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="0a273-115">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="0a273-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="0a273-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="0a273-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="0a273-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="0a273-118">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="0a273-118">MANAGED_EXCEPTION_UNHANDLED</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
> [!NOTE]
> <span data-ttu-id="0a273-119">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a273-119">The interface is available with .NET Native only.</span></span> <span data-ttu-id="0a273-120">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 `QueryInterface`를 호출하여 인터페이스 포인터를 검색하려고 하면 `E_NOINTERFACE`가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a273-120">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a273-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0a273-121">Requirements</span></span>  
 <span data-ttu-id="0a273-122">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0a273-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a273-123">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0a273-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0a273-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0a273-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0a273-125">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a273-125">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a273-126">참조</span><span class="sxs-lookup"><span data-stu-id="0a273-126">See also</span></span>

- [<span data-ttu-id="0a273-127">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0a273-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="0a273-128">디버깅</span><span class="sxs-lookup"><span data-stu-id="0a273-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
