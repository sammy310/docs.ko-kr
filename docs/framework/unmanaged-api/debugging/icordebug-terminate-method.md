---
title: ICorDebug::Terminate 메서드
ms.date: 03/30/2017
api_name:
- ICorDebug.Terminate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::Terminate
helpviewer_keywords:
- Terminate method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Terminate method [.NET Framework debugging]
ms.assetid: fffe5616-0896-4426-ab5e-21869b514883
topic_type:
- apiref
ms.openlocfilehash: 78838e9002cb3f5263395af9de255c54de47b6ae
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134026"
---
# <a name="icordebugterminate-method"></a><span data-ttu-id="32036-102">ICorDebug::Terminate 메서드</span><span class="sxs-lookup"><span data-stu-id="32036-102">ICorDebug::Terminate Method</span></span>
<span data-ttu-id="32036-103">`ICorDebug` 개체를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="32036-103">Terminates the `ICorDebug` object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="32036-104">디버깅 중인 모든 프로세스에 대해 [ICorDebugManagedCallback:: ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) 콜백이 수신 될 때까지 `Terminate`를 호출 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32036-104">`Terminate` should not be called until an [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) callback has been received for all processes being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32036-105">구문</span><span class="sxs-lookup"><span data-stu-id="32036-105">Syntax</span></span>  
  
```cpp  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="32036-106">주의</span><span class="sxs-lookup"><span data-stu-id="32036-106">Remarks</span></span>  
 <span data-ttu-id="32036-107">`ICorDebug` 개체가 더 이상 필요 하지 않은 경우 `Terminate`를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32036-107">`Terminate` must be called when the `ICorDebug` object is no longer needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32036-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="32036-108">Requirements</span></span>  
 <span data-ttu-id="32036-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="32036-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32036-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="32036-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="32036-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="32036-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="32036-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32036-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32036-113">참조</span><span class="sxs-lookup"><span data-stu-id="32036-113">See also</span></span>

- [<span data-ttu-id="32036-114">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="32036-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
