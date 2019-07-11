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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 350a3505345aa88d93f551309eb896ff52cc683d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67761152"
---
# <a name="icordebugmanagedcallback2destroyconnection-method"></a><span data-ttu-id="e8e80-102">ICorDebugManagedCallback2::DestroyConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="e8e80-102">ICorDebugManagedCallback2::DestroyConnection Method</span></span>
<span data-ttu-id="e8e80-103">지정한 연결 종료 되었다는 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="e8e80-103">Notifies the debugger that the specified connection has been terminated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8e80-104">구문</span><span class="sxs-lookup"><span data-stu-id="e8e80-104">Syntax</span></span>  
  
```cpp  
HRESULT DestroyConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8e80-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e8e80-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="e8e80-106">[in] 제거 된 연결을 포함 하는 프로세스를 나타내는 ICorDebugProcess 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e8e80-106">[in] A pointer to an ICorDebugProcess object that represents the process containing the connection that was destroyed.</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="e8e80-107">[in] 제거 된 연결의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e8e80-107">[in] The ID of the connection that was destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8e80-108">설명</span><span class="sxs-lookup"><span data-stu-id="e8e80-108">Remarks</span></span>  
 <span data-ttu-id="e8e80-109">A `DestroyConnection` 호스트를 호출할 때 콜백은 발생 [iclrdebugmanager:: Endconnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md) 에 [호스팅 API](../../../../docs/framework/unmanaged-api/hosting/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e8e80-109">A `DestroyConnection` callback will be fired when a host calls [ICLRDebugManager::EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8e80-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e8e80-110">Requirements</span></span>  
 <span data-ttu-id="e8e80-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e8e80-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8e80-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e8e80-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e8e80-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8e80-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8e80-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8e80-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8e80-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="e8e80-115">See also</span></span>

- [<span data-ttu-id="e8e80-116">ICorDebugManagedCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e8e80-116">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="e8e80-117">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e8e80-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
