---
title: ICorDebugManagedCallback::ExitProcess 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ExitProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitProcess
helpviewer_keywords:
- ExitProcess method, ICorDebugManagedCallback interface [.NET Framework debugging]
- ICorDebugManagedCallback::ExitProcess method [.NET Framework debugging]
ms.assetid: 63a7d47a-0d54-4e29-9767-9f09feaa38b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 04b8ac6751024e64cc866fce1cfe72fb42e41200
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760444"
---
# <a name="icordebugmanagedcallbackexitprocess-method"></a><span data-ttu-id="1ffc1-102">ICorDebugManagedCallback::ExitProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="1ffc1-102">ICorDebugManagedCallback::ExitProcess Method</span></span>
<span data-ttu-id="1ffc1-103">프로세스가 종료 되었는지 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="1ffc1-103">Notifies the debugger that a process has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ffc1-104">구문</span><span class="sxs-lookup"><span data-stu-id="1ffc1-104">Syntax</span></span>  
  
```cpp  
HRESULT ExitProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ffc1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1ffc1-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="1ffc1-106">[in] 프로세스를 나타내는 ICorDebugProcess 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1ffc1-106">[in] A pointer to an ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ffc1-107">설명</span><span class="sxs-lookup"><span data-stu-id="1ffc1-107">Remarks</span></span>  
 <span data-ttu-id="1ffc1-108">계속할 수 없습니다는 `ExitProcess` 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="1ffc1-108">You cannot continue from an `ExitProcess` event.</span></span> <span data-ttu-id="1ffc1-109">이 이벤트는 프로세스를 중지할 표시 되는 반면 다른 이벤트를 비동기적으로 발생 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ffc1-109">This event may fire asynchronously to other events while the process appears to be stopped.</span></span> <span data-ttu-id="1ffc1-110">일반적으로 외부 요인으로 인해 중지 하는 동안 프로세스를 종료 하는 경우 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ffc1-110">This can occur if the process terminates while stopped, usually due to some external force.</span></span>  
  
 <span data-ttu-id="1ffc1-111">CLR (공용 언어 런타임)을 이미 관리 되는 콜백을 전달 하 고, 경우이 이벤트 후 해당 콜백이 반환 될 때까지 지연 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ffc1-111">If the common language runtime (CLR) is already dispatching a managed callback, this event will be delayed until after that callback has returned.</span></span>  
  
 <span data-ttu-id="1ffc1-112">`ExitProcess` 이벤트는 종료 시 호출 보장 되는 유일한 종료/언로드 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="1ffc1-112">The `ExitProcess` event is the only exit/unload event that is guaranteed to get called on shutdown.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ffc1-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1ffc1-113">Requirements</span></span>  
 <span data-ttu-id="1ffc1-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1ffc1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ffc1-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1ffc1-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1ffc1-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1ffc1-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1ffc1-117">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ffc1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ffc1-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="1ffc1-118">See also</span></span>

- [<span data-ttu-id="1ffc1-119">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1ffc1-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
