---
title: ICorDebugVirtualUnwinder 인터페이스
ms.date: 03/30/2017
ms.assetid: a09e9ccc-0b37-43e3-95c1-bc5fa7ee5f42
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 639cfc514d2a206f0de72db4b0bac02b53305ae3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083402"
---
# <a name="icordebugvirtualunwinder-interface"></a><span data-ttu-id="af048-102">ICorDebugVirtualUnwinder 인터페이스</span><span class="sxs-lookup"><span data-stu-id="af048-102">ICorDebugVirtualUnwinder Interface</span></span>
<span data-ttu-id="af048-103">스택 해제에 도움이 되는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="af048-103">Provides methods to help in stack unwinding.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="af048-104">메서드</span><span class="sxs-lookup"><span data-stu-id="af048-104">Methods</span></span>  
  
|<span data-ttu-id="af048-105">메서드</span><span class="sxs-lookup"><span data-stu-id="af048-105">Method</span></span>|<span data-ttu-id="af048-106">이름</span><span class="sxs-lookup"><span data-stu-id="af048-106">Name</span></span>|  
|------------|----------|  
|[<span data-ttu-id="af048-107">GetContext 메서드</span><span class="sxs-lookup"><span data-stu-id="af048-107">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-getcontext-method.md)|<span data-ttu-id="af048-108">이 해제기의 현재 컨텍스트를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="af048-108">Gets the current context of this unwinder.</span></span>|  
|[<span data-ttu-id="af048-109">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="af048-109">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-next-method.md)|<span data-ttu-id="af048-110">호출자의 컨텍스트로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="af048-110">Advances to the caller's context.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af048-111">설명</span><span class="sxs-lookup"><span data-stu-id="af048-111">Remarks</span></span>  
 <span data-ttu-id="af048-112">`ICorDebugVirtualUnwinder` 인터페이스의 멤버는 스택 해제에 도움이 되도록 디버거에 의해 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="af048-112">The members of the `ICorDebugVirtualUnwinder` interface are implemented by the debugger to help in stack unwinding.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="af048-113">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af048-113">This interface is available with .NET Native only.</span></span> <span data-ttu-id="af048-114">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 이 인터페이스를 구현하는 경우 공용 언어 런타임에서 이 인터페이스를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="af048-114">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af048-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="af048-115">Requirements</span></span>  
 <span data-ttu-id="af048-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="af048-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af048-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="af048-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="af048-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af048-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="af048-119">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="af048-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="af048-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="af048-120">See also</span></span>

- [<span data-ttu-id="af048-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="af048-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="af048-122">디버깅</span><span class="sxs-lookup"><span data-stu-id="af048-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
