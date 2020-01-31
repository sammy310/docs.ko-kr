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
ms.openlocfilehash: 2d3f8360a1fb1164fd4e26f85246251409bee376
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788956"
---
# <a name="icordebugterminate-method"></a><span data-ttu-id="691d0-102">ICorDebug::Terminate 메서드</span><span class="sxs-lookup"><span data-stu-id="691d0-102">ICorDebug::Terminate Method</span></span>
<span data-ttu-id="691d0-103">`ICorDebug` 개체를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="691d0-103">Terminates the `ICorDebug` object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="691d0-104">디버깅 중인 모든 프로세스에 대해 [ICorDebugManagedCallback:: ExitProcess](icordebugmanagedcallback-exitprocess-method.md) 콜백이 수신 될 때까지 `Terminate`를 호출 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="691d0-104">`Terminate` should not be called until an [ICorDebugManagedCallback::ExitProcess](icordebugmanagedcallback-exitprocess-method.md) callback has been received for all processes being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="691d0-105">구문</span><span class="sxs-lookup"><span data-stu-id="691d0-105">Syntax</span></span>  
  
```cpp  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="691d0-106">주의</span><span class="sxs-lookup"><span data-stu-id="691d0-106">Remarks</span></span>  
 <span data-ttu-id="691d0-107">`ICorDebug` 개체가 더 이상 필요 하지 않은 경우 `Terminate`를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="691d0-107">`Terminate` must be called when the `ICorDebug` object is no longer needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="691d0-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="691d0-108">Requirements</span></span>  
 <span data-ttu-id="691d0-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="691d0-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="691d0-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="691d0-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="691d0-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="691d0-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="691d0-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="691d0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="691d0-113">참조</span><span class="sxs-lookup"><span data-stu-id="691d0-113">See also</span></span>

- [<span data-ttu-id="691d0-114">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="691d0-114">ICorDebug Interface</span></span>](icordebug-interface.md)
