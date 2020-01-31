---
title: ICorDebugModuleDebugEvent 인터페이스
ms.date: 03/30/2017
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
ms.openlocfilehash: a2c7eaa8a2c811c1696024d9af4b715cc49e7caa
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792893"
---
# <a name="icordebugmoduledebugevent-interface"></a><span data-ttu-id="da4f1-102">ICorDebugModuleDebugEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="da4f1-102">ICorDebugModuleDebugEvent Interface</span></span>
<span data-ttu-id="da4f1-103">모듈 수준 이벤트를 지원 하기 위해 [ICorDebugDebugEvent](icordebugdebugevent-interface.md) 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="da4f1-103">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support module-level events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="da4f1-104">메서드</span><span class="sxs-lookup"><span data-stu-id="da4f1-104">Methods</span></span>  
  
|<span data-ttu-id="da4f1-105">메서드</span><span class="sxs-lookup"><span data-stu-id="da4f1-105">Method</span></span>|<span data-ttu-id="da4f1-106">설명</span><span class="sxs-lookup"><span data-stu-id="da4f1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="da4f1-107">GetModule 메서드</span><span class="sxs-lookup"><span data-stu-id="da4f1-107">GetModule Method</span></span>](icordebugmoduledebugevent-getmodule-method.md)|<span data-ttu-id="da4f1-108">방금 로드 또는 언로드된 병합된 모듈을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="da4f1-108">Gets the merged module that was just loaded or unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da4f1-109">주의</span><span class="sxs-lookup"><span data-stu-id="da4f1-109">Remarks</span></span>  
 <span data-ttu-id="da4f1-110">[MODULE_LOADED](cordebugdebugeventkind-enumeration.md) 및 [MODULE_UNLOADED](cordebugdebugeventkind-enumeration.md) 이벤트 형식은이 인터페이스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="da4f1-110">The [MODULE_LOADED](cordebugdebugeventkind-enumeration.md) and [MODULE_UNLOADED](cordebugdebugeventkind-enumeration.md) event types implement this interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="da4f1-111">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da4f1-111">The interface is available with .NET Native only.</span></span> <span data-ttu-id="da4f1-112">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 `QueryInterface`를 호출하여 인터페이스 포인터를 검색하려고 하면 `E_NOINTERFACE`가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="da4f1-112">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da4f1-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="da4f1-113">Requirements</span></span>  
 <span data-ttu-id="da4f1-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="da4f1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da4f1-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="da4f1-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="da4f1-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da4f1-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da4f1-117">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da4f1-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da4f1-118">참조</span><span class="sxs-lookup"><span data-stu-id="da4f1-118">See also</span></span>

- [<span data-ttu-id="da4f1-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="da4f1-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="da4f1-120">디버깅</span><span class="sxs-lookup"><span data-stu-id="da4f1-120">Debugging</span></span>](index.md)
