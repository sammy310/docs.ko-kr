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
ms.openlocfilehash: 4380b8a3803e164aab7318821a9dbde32ecc3a0b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781748"
---
# <a name="icordebugmanagedcallbackexitprocess-method"></a><span data-ttu-id="2d895-102">ICorDebugManagedCallback::ExitProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="2d895-102">ICorDebugManagedCallback::ExitProcess Method</span></span>
<span data-ttu-id="2d895-103">프로세스가 종료 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="2d895-103">Notifies the debugger that a process has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d895-104">구문</span><span class="sxs-lookup"><span data-stu-id="2d895-104">Syntax</span></span>  
  
```cpp  
HRESULT ExitProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d895-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2d895-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="2d895-106">진행 프로세스를 나타내는 ICorDebugProcess 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2d895-106">[in] A pointer to an ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d895-107">주의</span><span class="sxs-lookup"><span data-stu-id="2d895-107">Remarks</span></span>  
 <span data-ttu-id="2d895-108">`ExitProcess` 이벤트는 계속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2d895-108">You cannot continue from an `ExitProcess` event.</span></span> <span data-ttu-id="2d895-109">프로세스가 중지 된 상태로 표시 되는 동안이 이벤트는 다른 이벤트에 대해 비동기적으로 실행 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d895-109">This event may fire asynchronously to other events while the process appears to be stopped.</span></span> <span data-ttu-id="2d895-110">이러한 문제는 일반적으로 일부 외부 force로 인해 중지 되는 동안 프로세스가 종료 되는 경우에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d895-110">This can occur if the process terminates while stopped, usually due to some external force.</span></span>  
  
 <span data-ttu-id="2d895-111">CLR (공용 언어 런타임)에서 이미 관리 되는 콜백을 디스패치할 경우이 이벤트는 해당 콜백이 반환 될 때까지 지연 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d895-111">If the common language runtime (CLR) is already dispatching a managed callback, this event will be delayed until after that callback has returned.</span></span>  
  
 <span data-ttu-id="2d895-112">`ExitProcess` 이벤트는 종료 시 호출 되도록 보장 되는 유일한 exit/unload 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="2d895-112">The `ExitProcess` event is the only exit/unload event that is guaranteed to get called on shutdown.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d895-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2d895-113">Requirements</span></span>  
 <span data-ttu-id="2d895-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2d895-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d895-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2d895-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2d895-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d895-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d895-117">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d895-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d895-118">참조</span><span class="sxs-lookup"><span data-stu-id="2d895-118">See also</span></span>

- [<span data-ttu-id="2d895-119">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2d895-119">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
