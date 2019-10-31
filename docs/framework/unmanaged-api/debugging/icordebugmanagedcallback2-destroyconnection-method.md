---
title: ICorDebugManagedCallback2::DestroyConnection 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.DestroyConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::DestroyConnection
helpviewer_keywords:
- DestroyConnection method [.NET Framework debugging]
- ICorDebugManagedCallback2::DestroyConnection method [.NET Framework debugging]
ms.assetid: cf7940e9-4558-4319-925c-09f6c98c8fcd
topic_type:
- apiref
ms.openlocfilehash: a64df9f821021547efd08045e9f67fee25173e5a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137435"
---
# <a name="icordebugmanagedcallback2destroyconnection-method"></a><span data-ttu-id="e662d-102">ICorDebugManagedCallback2::DestroyConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="e662d-102">ICorDebugManagedCallback2::DestroyConnection Method</span></span>
<span data-ttu-id="e662d-103">지정 된 연결이 종료 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="e662d-103">Notifies the debugger that the specified connection has been terminated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e662d-104">구문</span><span class="sxs-lookup"><span data-stu-id="e662d-104">Syntax</span></span>  
  
```cpp  
HRESULT DestroyConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e662d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e662d-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="e662d-106">진행 제거 된 연결을 포함 하는 프로세스를 나타내는 ICorDebugProcess 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e662d-106">[in] A pointer to an ICorDebugProcess object that represents the process containing the connection that was destroyed.</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="e662d-107">진행 제거 된 연결의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e662d-107">[in] The ID of the connection that was destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e662d-108">주의</span><span class="sxs-lookup"><span data-stu-id="e662d-108">Remarks</span></span>  
 <span data-ttu-id="e662d-109">호스트에서 [호스팅 API](../../../../docs/framework/unmanaged-api/hosting/index.md)의 [ICLRDebugManager:: endconnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md) 을 호출 하면 `DestroyConnection` 콜백이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="e662d-109">A `DestroyConnection` callback will be fired when a host calls [ICLRDebugManager::EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e662d-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e662d-110">Requirements</span></span>  
 <span data-ttu-id="e662d-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e662d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e662d-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e662d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e662d-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e662d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e662d-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e662d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e662d-115">참조</span><span class="sxs-lookup"><span data-stu-id="e662d-115">See also</span></span>

- [<span data-ttu-id="e662d-116">ICorDebugManagedCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e662d-116">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="e662d-117">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e662d-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
