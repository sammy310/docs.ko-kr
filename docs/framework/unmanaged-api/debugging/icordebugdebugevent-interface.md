---
title: ICorDebugDebugEvent 인터페이스
ms.date: 03/30/2017
ms.assetid: a226737a-cb99-4e97-bd94-9a37094ded41
ms.openlocfilehash: ea42faa4001fa880354690df1551de3be767e683
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137031"
---
# <a name="icordebugdebugevent-interface"></a><span data-ttu-id="45b0b-102">ICorDebugDebugEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="45b0b-102">ICorDebugDebugEvent Interface</span></span>
<span data-ttu-id="45b0b-103">모든 `ICorDebug` 디버그 이벤트가 파생되는 기본 인터페이스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="45b0b-103">Defines the base interface from which all `ICorDebug` debug events derive.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="45b0b-104">메서드</span><span class="sxs-lookup"><span data-stu-id="45b0b-104">Methods</span></span>  
  
|<span data-ttu-id="45b0b-105">메서드</span><span class="sxs-lookup"><span data-stu-id="45b0b-105">Method</span></span>|<span data-ttu-id="45b0b-106">설명</span><span class="sxs-lookup"><span data-stu-id="45b0b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="45b0b-107">GetEventKind 메서드</span><span class="sxs-lookup"><span data-stu-id="45b0b-107">GetEventKind Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md)|<span data-ttu-id="45b0b-108">이 `ICorDebugDebugEvent` 개체가 나타내는 이벤트의 종류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="45b0b-108">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>|  
|[<span data-ttu-id="45b0b-109">GetThread 메서드</span><span class="sxs-lookup"><span data-stu-id="45b0b-109">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-getthread-method.md)|<span data-ttu-id="45b0b-110">이벤트가 발생한 스레드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="45b0b-110">Gets the thread on which the event occurred.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45b0b-111">주의</span><span class="sxs-lookup"><span data-stu-id="45b0b-111">Remarks</span></span>  
 <span data-ttu-id="45b0b-112">다음 인터페이스는 `ICorDebugDebugEvent` 인터페이스에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="45b0b-112">The following interfaces are derived from the `ICorDebugDebugEvent` interface:</span></span>  
  
- [<span data-ttu-id="45b0b-113">ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="45b0b-113">ICorDebugExceptionDebugEvent</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
  
- [<span data-ttu-id="45b0b-114">ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="45b0b-114">ICorDebugModuleDebugEvent</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)  
  
> [!NOTE]
> <span data-ttu-id="45b0b-115">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45b0b-115">The interface is available with .NET Native only.</span></span> <span data-ttu-id="45b0b-116">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 `QueryInterface`를 호출하여 인터페이스 포인터를 검색하려고 하면 `E_NOINTERFACE`가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="45b0b-116">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45b0b-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="45b0b-117">Requirements</span></span>  
 <span data-ttu-id="45b0b-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45b0b-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45b0b-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="45b0b-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="45b0b-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45b0b-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45b0b-121">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45b0b-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45b0b-122">참조</span><span class="sxs-lookup"><span data-stu-id="45b0b-122">See also</span></span>

- [<span data-ttu-id="45b0b-123">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="45b0b-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="45b0b-124">디버깅</span><span class="sxs-lookup"><span data-stu-id="45b0b-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
