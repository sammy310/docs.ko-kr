---
description: '자세히 알아보기: ICorDebugDebugEvent 인터페이스'
title: ICorDebugDebugEvent 인터페이스
ms.date: 03/30/2017
ms.assetid: a226737a-cb99-4e97-bd94-9a37094ded41
ms.openlocfilehash: 5735be22b76e9f74847bb5138c00130f28dbfc96
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764309"
---
# <a name="icordebugdebugevent-interface"></a><span data-ttu-id="c23b5-103">ICorDebugDebugEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c23b5-103">ICorDebugDebugEvent Interface</span></span>

<span data-ttu-id="c23b5-104">모든 `ICorDebug` 디버그 이벤트가 파생되는 기본 인터페이스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c23b5-104">Defines the base interface from which all `ICorDebug` debug events derive.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c23b5-105">메서드</span><span class="sxs-lookup"><span data-stu-id="c23b5-105">Methods</span></span>  
  
|<span data-ttu-id="c23b5-106">메서드</span><span class="sxs-lookup"><span data-stu-id="c23b5-106">Method</span></span>|<span data-ttu-id="c23b5-107">설명</span><span class="sxs-lookup"><span data-stu-id="c23b5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c23b5-108">GetEventKind 메서드</span><span class="sxs-lookup"><span data-stu-id="c23b5-108">GetEventKind Method</span></span>](icordebugdebugevent-geteventkind-method.md)|<span data-ttu-id="c23b5-109">이 `ICorDebugDebugEvent` 개체가 나타내는 이벤트의 종류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c23b5-109">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>|  
|[<span data-ttu-id="c23b5-110">GetThread 메서드</span><span class="sxs-lookup"><span data-stu-id="c23b5-110">GetThread Method</span></span>](icordebugdebugevent-getthread-method.md)|<span data-ttu-id="c23b5-111">이벤트가 발생한 스레드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c23b5-111">Gets the thread on which the event occurred.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c23b5-112">설명</span><span class="sxs-lookup"><span data-stu-id="c23b5-112">Remarks</span></span>  

 <span data-ttu-id="c23b5-113">다음 인터페이스는 `ICorDebugDebugEvent` 인터페이스에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="c23b5-113">The following interfaces are derived from the `ICorDebugDebugEvent` interface:</span></span>  
  
- [<span data-ttu-id="c23b5-114">ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="c23b5-114">ICorDebugExceptionDebugEvent</span></span>](icordebugexceptiondebugevent-interface.md)  
  
- [<span data-ttu-id="c23b5-115">ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="c23b5-115">ICorDebugModuleDebugEvent</span></span>](icordebugmoduledebugevent-interface.md)  
  
> [!NOTE]
> <span data-ttu-id="c23b5-116">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c23b5-116">The interface is available with .NET Native only.</span></span> <span data-ttu-id="c23b5-117">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 `QueryInterface`를 호출하여 인터페이스 포인터를 검색하려고 하면 `E_NOINTERFACE`가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="c23b5-117">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c23b5-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c23b5-118">Requirements</span></span>  

 <span data-ttu-id="c23b5-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c23b5-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c23b5-120">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c23b5-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c23b5-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c23b5-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c23b5-122">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c23b5-122">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c23b5-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c23b5-123">See also</span></span>

- [<span data-ttu-id="c23b5-124">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c23b5-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="c23b5-125">디버깅</span><span class="sxs-lookup"><span data-stu-id="c23b5-125">Debugging</span></span>](index.md)
