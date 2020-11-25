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
ms.openlocfilehash: cf9c9d11c4725908fcf7ff4a0c91882b70a80190
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723378"
---
# <a name="icordebugterminate-method"></a><span data-ttu-id="3648c-102">ICorDebug::Terminate 메서드</span><span class="sxs-lookup"><span data-stu-id="3648c-102">ICorDebug::Terminate Method</span></span>

<span data-ttu-id="3648c-103">개체를 종료 `ICorDebug` 합니다.</span><span class="sxs-lookup"><span data-stu-id="3648c-103">Terminates the `ICorDebug` object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3648c-104">`Terminate` 디버깅 중인 모든 프로세스에 대해 [ICorDebugManagedCallback:: ExitProcess](icordebugmanagedcallback-exitprocess-method.md) 콜백이 수신 될 때까지 호출 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3648c-104">`Terminate` should not be called until an [ICorDebugManagedCallback::ExitProcess](icordebugmanagedcallback-exitprocess-method.md) callback has been received for all processes being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3648c-105">구문</span><span class="sxs-lookup"><span data-stu-id="3648c-105">Syntax</span></span>  
  
```cpp  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="3648c-106">설명</span><span class="sxs-lookup"><span data-stu-id="3648c-106">Remarks</span></span>  

 <span data-ttu-id="3648c-107">`Terminate``ICorDebug`개체가 더 이상 필요 하지 않을 때를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3648c-107">`Terminate` must be called when the `ICorDebug` object is no longer needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3648c-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3648c-108">Requirements</span></span>  

 <span data-ttu-id="3648c-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3648c-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3648c-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3648c-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3648c-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3648c-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3648c-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3648c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3648c-113">참조</span><span class="sxs-lookup"><span data-stu-id="3648c-113">See also</span></span>

- [<span data-ttu-id="3648c-114">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3648c-114">ICorDebug Interface</span></span>](icordebug-interface.md)
