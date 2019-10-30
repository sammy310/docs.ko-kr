---
title: ICorDebugRuntimeUnwindableFrame 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugUnwindableFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnwindableFrame
helpviewer_keywords:
- ICorDebugUnwindableFrame interface [.NET Framework debugging]
ms.assetid: cd6a3982-6ed3-4909-808d-a66055e813e0
topic_type:
- apiref
ms.openlocfilehash: 2902744b6af3c7b2bd4def73b04807ce3333a8a1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131885"
---
# <a name="icordebugruntimeunwindableframe-interface"></a><span data-ttu-id="c75f5-102">ICorDebugRuntimeUnwindableFrame 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c75f5-102">ICorDebugRuntimeUnwindableFrame Interface</span></span>
<span data-ttu-id="c75f5-103">프레임을 해제하는 데 CLR(공용 언어 런타임)을 필요로 하는 관리되지 않는 메서드에 대한 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c75f5-103">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c75f5-104">주의</span><span class="sxs-lookup"><span data-stu-id="c75f5-104">Remarks</span></span>  
 <span data-ttu-id="c75f5-105">`ICorDebugRuntimeUnwindableFrame`는 ICorDebugFrame 인터페이스의 특수 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="c75f5-105">`ICorDebugRuntimeUnwindableFrame` is a specialized version of the ICorDebugFrame interface.</span></span> <span data-ttu-id="c75f5-106">런타임이 현재 스택의 프레임을 해제 해야 하는 관리 되지 않는 메서드에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c75f5-106">It is used by unmanaged methods that require the runtime to unwind a frame on the current stack.</span></span> <span data-ttu-id="c75f5-107">기존 해제 규칙은 JIT 컴파일된 코드를 사용 하지 않기 때문에 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c75f5-107">Existing unwinding conventions do not work, because they do not use JIT-compiled code.</span></span> <span data-ttu-id="c75f5-108">디버거는 unwindable 프레임을 볼 때 [ICorDebugStackWalk:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md) 메서드를 사용 하 여 해제 해야 하지만 검사를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c75f5-108">When the debugger sees an unwindable frame, it should use the [ICorDebugStackWalk::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md) method to unwind it, but it should perform inspection itself.</span></span> <span data-ttu-id="c75f5-109">디버거는 `ICorDebugRuntimeUnwindableFrame`를 받을 때 [ICorDebugStackWalk:: getcontext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) 메서드를 호출 하 여 프레임의 컨텍스트를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c75f5-109">When the debugger receives an `ICorDebugRuntimeUnwindableFrame`, it can call the [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) method to retrieve the context of the frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c75f5-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c75f5-110">Requirements</span></span>  
 <span data-ttu-id="c75f5-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c75f5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c75f5-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c75f5-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c75f5-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c75f5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c75f5-114">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c75f5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c75f5-115">참조</span><span class="sxs-lookup"><span data-stu-id="c75f5-115">See also</span></span>

- [<span data-ttu-id="c75f5-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c75f5-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="c75f5-117">디버깅</span><span class="sxs-lookup"><span data-stu-id="c75f5-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
