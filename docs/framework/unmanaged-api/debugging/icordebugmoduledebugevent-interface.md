---
title: ICorDebugModuleDebugEvent 인터페이스
ms.date: 03/30/2017
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7bf1fa21872c710ebc69c45e9980aeaa577a45fc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160916"
---
# <a name="icordebugmoduledebugevent-interface"></a><span data-ttu-id="493a5-102">ICorDebugModuleDebugEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="493a5-102">ICorDebugModuleDebugEvent Interface</span></span>
<span data-ttu-id="493a5-103">확장 된 [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) 모듈 수준 이벤트를 지 원하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="493a5-103">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support module-level events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="493a5-104">메서드</span><span class="sxs-lookup"><span data-stu-id="493a5-104">Methods</span></span>  
  
|<span data-ttu-id="493a5-105">메서드</span><span class="sxs-lookup"><span data-stu-id="493a5-105">Method</span></span>|<span data-ttu-id="493a5-106">설명</span><span class="sxs-lookup"><span data-stu-id="493a5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="493a5-107">GetModule 메서드</span><span class="sxs-lookup"><span data-stu-id="493a5-107">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-getmodule-method.md)|<span data-ttu-id="493a5-108">방금 로드 또는 언로드된 병합된 모듈을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="493a5-108">Gets the merged module that was just loaded or unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="493a5-109">설명</span><span class="sxs-lookup"><span data-stu-id="493a5-109">Remarks</span></span>  
 <span data-ttu-id="493a5-110">합니다 [MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) 하 고 [MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) 이벤트 유형을이 인터페이스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="493a5-110">The [MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) and [MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) event types implement this interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="493a5-111">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="493a5-111">The interface is available with .NET Native only.</span></span> <span data-ttu-id="493a5-112">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 `QueryInterface`를 호출하여 인터페이스 포인터를 검색하려고 하면 `E_NOINTERFACE`가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="493a5-112">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="493a5-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="493a5-113">Requirements</span></span>  
 <span data-ttu-id="493a5-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="493a5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="493a5-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="493a5-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="493a5-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="493a5-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="493a5-117">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="493a5-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="493a5-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="493a5-118">See also</span></span>

- [<span data-ttu-id="493a5-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="493a5-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="493a5-120">디버깅</span><span class="sxs-lookup"><span data-stu-id="493a5-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
