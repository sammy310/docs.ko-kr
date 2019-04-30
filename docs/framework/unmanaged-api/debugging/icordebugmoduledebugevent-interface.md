---
title: ICorDebugModuleDebugEvent 인터페이스
ms.date: 03/30/2017
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7bf1fa21872c710ebc69c45e9980aeaa577a45fc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942469"
---
# <a name="icordebugmoduledebugevent-interface"></a><span data-ttu-id="a5a1d-102">ICorDebugModuleDebugEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a5a1d-102">ICorDebugModuleDebugEvent Interface</span></span>
<span data-ttu-id="a5a1d-103">확장 된 [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) 모듈 수준 이벤트를 지 원하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="a5a1d-103">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support module-level events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a5a1d-104">메서드</span><span class="sxs-lookup"><span data-stu-id="a5a1d-104">Methods</span></span>  
  
|<span data-ttu-id="a5a1d-105">메서드</span><span class="sxs-lookup"><span data-stu-id="a5a1d-105">Method</span></span>|<span data-ttu-id="a5a1d-106">설명</span><span class="sxs-lookup"><span data-stu-id="a5a1d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a5a1d-107">GetModule 메서드</span><span class="sxs-lookup"><span data-stu-id="a5a1d-107">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-getmodule-method.md)|<span data-ttu-id="a5a1d-108">방금 로드 또는 언로드된 병합된 모듈을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a5a1d-108">Gets the merged module that was just loaded or unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5a1d-109">설명</span><span class="sxs-lookup"><span data-stu-id="a5a1d-109">Remarks</span></span>  
 <span data-ttu-id="a5a1d-110">합니다 [MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) 하 고 [MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) 이벤트 유형을이 인터페이스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5a1d-110">The [MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) and [MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) event types implement this interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5a1d-111">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5a1d-111">The interface is available with .NET Native only.</span></span> <span data-ttu-id="a5a1d-112">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 `QueryInterface`를 호출하여 인터페이스 포인터를 검색하려고 하면 `E_NOINTERFACE`가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5a1d-112">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5a1d-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a5a1d-113">Requirements</span></span>  
 <span data-ttu-id="a5a1d-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a5a1d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5a1d-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a5a1d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a5a1d-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5a1d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5a1d-117">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5a1d-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5a1d-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="a5a1d-118">See also</span></span>

- [<span data-ttu-id="a5a1d-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a5a1d-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="a5a1d-120">디버깅</span><span class="sxs-lookup"><span data-stu-id="a5a1d-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
