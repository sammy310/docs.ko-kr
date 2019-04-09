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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bf6bc73683a6c37ceaaffc635a58803b71c3b6cd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134201"
---
# <a name="icordebugruntimeunwindableframe-interface"></a><span data-ttu-id="a4092-102">ICorDebugRuntimeUnwindableFrame 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a4092-102">ICorDebugRuntimeUnwindableFrame Interface</span></span>
<span data-ttu-id="a4092-103">프레임을 해제하는 데 CLR(공용 언어 런타임)을 필요로 하는 관리되지 않는 메서드에 대한 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a4092-103">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4092-104">설명</span><span class="sxs-lookup"><span data-stu-id="a4092-104">Remarks</span></span>  
 `ICorDebugRuntimeUnwindableFrame` <span data-ttu-id="a4092-105">ICorDebugFrame 인터페이스의 특수 버전이입니다.</span><span class="sxs-lookup"><span data-stu-id="a4092-105">is a specialized version of the ICorDebugFrame interface.</span></span> <span data-ttu-id="a4092-106">런타임에서 현재 스택 프레임 해제 필요로 하는 관리 되지 않는 방법으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4092-106">It is used by unmanaged methods that require the runtime to unwind a frame on the current stack.</span></span> <span data-ttu-id="a4092-107">JIT 컴파일 코드를 사용 하지 않으므로 기존 해제 규칙 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4092-107">Existing unwinding conventions do not work, because they do not use JIT-compiled code.</span></span> <span data-ttu-id="a4092-108">디버거는 해제할 수 있는 프레임을 인식 하는 경우 사용 해야 합니다 [icordebugstackwalk:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md) 있지만, 해당 해제 방법 자체 검사를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4092-108">When the debugger sees an unwindable frame, it should use the [ICorDebugStackWalk::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md) method to unwind it, but it should perform inspection itself.</span></span> <span data-ttu-id="a4092-109">디버거 받으면를 `ICorDebugRuntimeUnwindableFrame`를 호출할 수 있습니다 합니다 [icordebugstackwalk:: Getcontext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) 프레임의 컨텍스트를 검색 하는 방법.</span><span class="sxs-lookup"><span data-stu-id="a4092-109">When the debugger receives an `ICorDebugRuntimeUnwindableFrame`, it can call the [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) method to retrieve the context of the frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4092-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a4092-110">Requirements</span></span>  
 <span data-ttu-id="a4092-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a4092-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4092-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a4092-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a4092-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4092-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="a4092-114">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="a4092-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a4092-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="a4092-115">See also</span></span>

- [<span data-ttu-id="a4092-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a4092-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="a4092-117">디버깅</span><span class="sxs-lookup"><span data-stu-id="a4092-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
