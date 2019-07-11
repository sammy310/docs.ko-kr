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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3037fc704ffc3aac4d050cef7857261f138f7d35
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738064"
---
# <a name="icordebugterminate-method"></a><span data-ttu-id="beec0-102">ICorDebug::Terminate 메서드</span><span class="sxs-lookup"><span data-stu-id="beec0-102">ICorDebug::Terminate Method</span></span>
<span data-ttu-id="beec0-103">종료는 `ICorDebug` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="beec0-103">Terminates the `ICorDebug` object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="beec0-104">`Terminate` 될 때까지 호출 되지 않아야는 [icordebugmanagedcallback:: Exitprocess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) 디버깅 중인 모든 프로세스에 대 한 콜백 받았습니다.</span><span class="sxs-lookup"><span data-stu-id="beec0-104">`Terminate` should not be called until an [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) callback has been received for all processes being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="beec0-105">구문</span><span class="sxs-lookup"><span data-stu-id="beec0-105">Syntax</span></span>  
  
```cpp  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="beec0-106">설명</span><span class="sxs-lookup"><span data-stu-id="beec0-106">Remarks</span></span>  
 <span data-ttu-id="beec0-107">`Terminate` 호출 해야 합니다는 `ICorDebug` 개체가 더 이상 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="beec0-107">`Terminate` must be called when the `ICorDebug` object is no longer needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="beec0-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="beec0-108">Requirements</span></span>  
 <span data-ttu-id="beec0-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="beec0-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="beec0-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="beec0-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="beec0-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="beec0-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="beec0-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="beec0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="beec0-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="beec0-113">See also</span></span>

- [<span data-ttu-id="beec0-114">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="beec0-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
