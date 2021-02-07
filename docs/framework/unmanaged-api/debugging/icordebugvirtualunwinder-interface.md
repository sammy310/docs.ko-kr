---
description: '자세히 알아보기: ICorDebugVirtualUnwinder 인터페이스'
title: ICorDebugVirtualUnwinder 인터페이스
ms.date: 03/30/2017
ms.assetid: a09e9ccc-0b37-43e3-95c1-bc5fa7ee5f42
ms.openlocfilehash: e941ace2e7f72c9f7956c03bae19f9b92094b338
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99738080"
---
# <a name="icordebugvirtualunwinder-interface"></a><span data-ttu-id="5edbb-103">ICorDebugVirtualUnwinder 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5edbb-103">ICorDebugVirtualUnwinder Interface</span></span>

<span data-ttu-id="5edbb-104">스택 해제에 도움이 되는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5edbb-104">Provides methods to help in stack unwinding.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5edbb-105">메서드</span><span class="sxs-lookup"><span data-stu-id="5edbb-105">Methods</span></span>  
  
|<span data-ttu-id="5edbb-106">메서드</span><span class="sxs-lookup"><span data-stu-id="5edbb-106">Method</span></span>|<span data-ttu-id="5edbb-107">Name</span><span class="sxs-lookup"><span data-stu-id="5edbb-107">Name</span></span>|  
|------------|----------|  
|[<span data-ttu-id="5edbb-108">GetContext 메서드</span><span class="sxs-lookup"><span data-stu-id="5edbb-108">GetContext Method</span></span>](icordebugvirtualunwinder-getcontext-method.md)|<span data-ttu-id="5edbb-109">이 해제기의 현재 컨텍스트를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5edbb-109">Gets the current context of this unwinder.</span></span>|  
|[<span data-ttu-id="5edbb-110">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="5edbb-110">Next Method</span></span>](icordebugvirtualunwinder-next-method.md)|<span data-ttu-id="5edbb-111">호출자의 컨텍스트로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5edbb-111">Advances to the caller's context.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5edbb-112">설명</span><span class="sxs-lookup"><span data-stu-id="5edbb-112">Remarks</span></span>  

 <span data-ttu-id="5edbb-113">`ICorDebugVirtualUnwinder` 인터페이스의 멤버는 스택 해제에 도움이 되도록 디버거에 의해 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="5edbb-113">The members of the `ICorDebugVirtualUnwinder` interface are implemented by the debugger to help in stack unwinding.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5edbb-114">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5edbb-114">This interface is available with .NET Native only.</span></span> <span data-ttu-id="5edbb-115">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 이 인터페이스를 구현하는 경우 공용 언어 런타임에서 이 인터페이스를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="5edbb-115">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5edbb-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5edbb-116">Requirements</span></span>  

 <span data-ttu-id="5edbb-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5edbb-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5edbb-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5edbb-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5edbb-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5edbb-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5edbb-120">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5edbb-120">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5edbb-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5edbb-121">See also</span></span>

- [<span data-ttu-id="5edbb-122">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5edbb-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="5edbb-123">디버깅</span><span class="sxs-lookup"><span data-stu-id="5edbb-123">Debugging</span></span>](index.md)
