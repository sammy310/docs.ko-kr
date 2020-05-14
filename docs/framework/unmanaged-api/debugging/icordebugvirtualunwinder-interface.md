---
title: ICorDebugVirtualUnwinder 인터페이스
ms.date: 03/30/2017
ms.assetid: a09e9ccc-0b37-43e3-95c1-bc5fa7ee5f42
ms.openlocfilehash: 59ecf3da4b44af7b04dec26fbc3ea182c185d04a
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396448"
---
# <a name="icordebugvirtualunwinder-interface"></a><span data-ttu-id="5664a-102">ICorDebugVirtualUnwinder 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5664a-102">ICorDebugVirtualUnwinder Interface</span></span>
<span data-ttu-id="5664a-103">스택 해제에 도움이 되는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5664a-103">Provides methods to help in stack unwinding.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5664a-104">메서드</span><span class="sxs-lookup"><span data-stu-id="5664a-104">Methods</span></span>  
  
|<span data-ttu-id="5664a-105">메서드</span><span class="sxs-lookup"><span data-stu-id="5664a-105">Method</span></span>|<span data-ttu-id="5664a-106">속성</span><span class="sxs-lookup"><span data-stu-id="5664a-106">Name</span></span>|  
|------------|----------|  
|[<span data-ttu-id="5664a-107">GetContext 메서드</span><span class="sxs-lookup"><span data-stu-id="5664a-107">GetContext Method</span></span>](icordebugvirtualunwinder-getcontext-method.md)|<span data-ttu-id="5664a-108">이 해제기의 현재 컨텍스트를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5664a-108">Gets the current context of this unwinder.</span></span>|  
|[<span data-ttu-id="5664a-109">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="5664a-109">Next Method</span></span>](icordebugvirtualunwinder-next-method.md)|<span data-ttu-id="5664a-110">호출자의 컨텍스트로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5664a-110">Advances to the caller's context.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5664a-111">설명</span><span class="sxs-lookup"><span data-stu-id="5664a-111">Remarks</span></span>  
 <span data-ttu-id="5664a-112">`ICorDebugVirtualUnwinder` 인터페이스의 멤버는 스택 해제에 도움이 되도록 디버거에 의해 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="5664a-112">The members of the `ICorDebugVirtualUnwinder` interface are implemented by the debugger to help in stack unwinding.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5664a-113">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5664a-113">This interface is available with .NET Native only.</span></span> <span data-ttu-id="5664a-114">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 이 인터페이스를 구현하는 경우 공용 언어 런타임에서 이 인터페이스를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="5664a-114">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5664a-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5664a-115">Requirements</span></span>  
 <span data-ttu-id="5664a-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5664a-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5664a-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5664a-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5664a-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5664a-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5664a-119">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5664a-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5664a-120">참조</span><span class="sxs-lookup"><span data-stu-id="5664a-120">See also</span></span>

- [<span data-ttu-id="5664a-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5664a-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="5664a-122">디버깅</span><span class="sxs-lookup"><span data-stu-id="5664a-122">Debugging</span></span>](index.md)
