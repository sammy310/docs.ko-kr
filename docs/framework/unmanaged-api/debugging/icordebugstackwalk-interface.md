---
title: ICorDebugStackWalk 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk
helpviewer_keywords:
- ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 16d695e8-975d-431b-8421-e9e6c3e3f476
topic_type:
- apiref
ms.openlocfilehash: a6283d699263dc9b79e457010f31923f77443129
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791885"
---
# <a name="icordebugstackwalk-interface"></a><span data-ttu-id="faf91-102">ICorDebugStackWalk 인터페이스</span><span class="sxs-lookup"><span data-stu-id="faf91-102">ICorDebugStackWalk Interface</span></span>
<span data-ttu-id="faf91-103">스레드 스택에서 관리되는 메서드나 프레임을 가져오기 위한 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="faf91-103">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="faf91-104">메서드</span><span class="sxs-lookup"><span data-stu-id="faf91-104">Methods</span></span>  
  
|<span data-ttu-id="faf91-105">메서드</span><span class="sxs-lookup"><span data-stu-id="faf91-105">Method</span></span>|<span data-ttu-id="faf91-106">설명</span><span class="sxs-lookup"><span data-stu-id="faf91-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="faf91-107">GetContext 메서드</span><span class="sxs-lookup"><span data-stu-id="faf91-107">GetContext Method</span></span>](icordebugstackwalk-getcontext-method.md)|<span data-ttu-id="faf91-108">`ICorDebugStackWalk` 개체의 현재 프레임에 대 한 컨텍스트를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="faf91-108">Returns the context for the current frame in the `ICorDebugStackWalk` object.</span></span>|  
|[<span data-ttu-id="faf91-109">SetContext 메서드</span><span class="sxs-lookup"><span data-stu-id="faf91-109">SetContext Method</span></span>](icordebugstackwalk-setcontext-method.md)|<span data-ttu-id="faf91-110">`ICorDebugStackWalk` 개체의 현재 컨텍스트를 스레드의 올바른 컨텍스트로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="faf91-110">Sets the `ICorDebugStackWalk` object’s current context to a valid context for the thread.</span></span>|  
|[<span data-ttu-id="faf91-111">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="faf91-111">Next Method</span></span>](icordebugstackwalk-next-method.md)|<span data-ttu-id="faf91-112">`ICorDebugStackWalk` 개체를 다음 프레임으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="faf91-112">Moves the `ICorDebugStackWalk` object to the next frame.</span></span>|  
|[<span data-ttu-id="faf91-113">GetFrame 메서드</span><span class="sxs-lookup"><span data-stu-id="faf91-113">GetFrame Method</span></span>](icordebugstackwalk-getframe-method.md)|<span data-ttu-id="faf91-114">`ICorDebugStackWalk` 개체의 현재 프레임을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="faf91-114">Gets the current frame in the `ICorDebugStackWalk` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="faf91-115">주의</span><span class="sxs-lookup"><span data-stu-id="faf91-115">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="faf91-116">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="faf91-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="faf91-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="faf91-117">Requirements</span></span>  
 <span data-ttu-id="faf91-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="faf91-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="faf91-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="faf91-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="faf91-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="faf91-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="faf91-121">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="faf91-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faf91-122">참조</span><span class="sxs-lookup"><span data-stu-id="faf91-122">See also</span></span>

- [<span data-ttu-id="faf91-123">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="faf91-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="faf91-124">디버깅</span><span class="sxs-lookup"><span data-stu-id="faf91-124">Debugging</span></span>](index.md)
