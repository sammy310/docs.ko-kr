---
description: '자세히 알아보기: ICorDebugModuleDebugEvent 인터페이스'
title: ICorDebugModuleDebugEvent 인터페이스
ms.date: 03/30/2017
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
ms.openlocfilehash: 0c2d43d7b04caeea0407ede23f0df6e278d60c92
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801035"
---
# <a name="icordebugmoduledebugevent-interface"></a><span data-ttu-id="fc2f9-103">ICorDebugModuleDebugEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fc2f9-103">ICorDebugModuleDebugEvent Interface</span></span>

<span data-ttu-id="fc2f9-104">모듈 수준 이벤트를 지원 하기 위해 [ICorDebugDebugEvent](icordebugdebugevent-interface.md) 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc2f9-104">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support module-level events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fc2f9-105">메서드</span><span class="sxs-lookup"><span data-stu-id="fc2f9-105">Methods</span></span>  
  
|<span data-ttu-id="fc2f9-106">메서드</span><span class="sxs-lookup"><span data-stu-id="fc2f9-106">Method</span></span>|<span data-ttu-id="fc2f9-107">설명</span><span class="sxs-lookup"><span data-stu-id="fc2f9-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fc2f9-108">GetModule 메서드</span><span class="sxs-lookup"><span data-stu-id="fc2f9-108">GetModule Method</span></span>](icordebugmoduledebugevent-getmodule-method.md)|<span data-ttu-id="fc2f9-109">방금 로드 또는 언로드된 병합된 모듈을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fc2f9-109">Gets the merged module that was just loaded or unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc2f9-110">설명</span><span class="sxs-lookup"><span data-stu-id="fc2f9-110">Remarks</span></span>  

 <span data-ttu-id="fc2f9-111">[MODULE_LOADED](cordebugdebugeventkind-enumeration.md) 및 [MODULE_UNLOADED](cordebugdebugeventkind-enumeration.md) 이벤트 형식은이 인터페이스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc2f9-111">The [MODULE_LOADED](cordebugdebugeventkind-enumeration.md) and [MODULE_UNLOADED](cordebugdebugeventkind-enumeration.md) event types implement this interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fc2f9-112">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc2f9-112">The interface is available with .NET Native only.</span></span> <span data-ttu-id="fc2f9-113">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 `QueryInterface`를 호출하여 인터페이스 포인터를 검색하려고 하면 `E_NOINTERFACE`가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc2f9-113">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc2f9-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fc2f9-114">Requirements</span></span>  

 <span data-ttu-id="fc2f9-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fc2f9-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc2f9-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc2f9-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc2f9-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc2f9-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc2f9-118">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc2f9-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc2f9-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fc2f9-119">See also</span></span>

- [<span data-ttu-id="fc2f9-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fc2f9-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="fc2f9-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="fc2f9-121">Debugging</span></span>](index.md)
