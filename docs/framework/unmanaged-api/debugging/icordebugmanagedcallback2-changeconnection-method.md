---
title: ICorDebugManagedCallback2::ChangeConnection 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.ChangeConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::ChangeConnection
helpviewer_keywords:
- ICorDebugManagedCallback2::ChangeConnection method [.NET Framework debugging]
- ChangeConnection method [.NET Framework debugging]
ms.assetid: 7263f9a9-4c0b-4d82-a181-288873fb2b18
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b4eeecc22db5786f66b3d484b521989e71817d8e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995126"
---
# <a name="icordebugmanagedcallback2changeconnection-method"></a><span data-ttu-id="6a58a-102">ICorDebugManagedCallback2::ChangeConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="6a58a-102">ICorDebugManagedCallback2::ChangeConnection Method</span></span>
<span data-ttu-id="6a58a-103">지정 된 연결과 관련 된 작업 집합이 변경 된 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="6a58a-103">Notifies the debugger that the set of tasks associated with the specified connection has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a58a-104">구문</span><span class="sxs-lookup"><span data-stu-id="6a58a-104">Syntax</span></span>  
  
```  
HRESULT ChangeConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a58a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6a58a-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="6a58a-106">[in] 변경 된 연결을 포함 하는 프로세스를 나타내는 "ICorDebugProcess" 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6a58a-106">[in] A pointer to an "ICorDebugProcess" object that represents the process containing the connection that changed.</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="6a58a-107">[in] 변경 하는 연결의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6a58a-107">[in] The ID of the connection that changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6a58a-108">설명</span><span class="sxs-lookup"><span data-stu-id="6a58a-108">Remarks</span></span>  
 <span data-ttu-id="6a58a-109">`ChangeConnection` 콜백 중 다음과 같은 경우에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a58a-109">A `ChangeConnection` callback will be fired in either of the following cases:</span></span>  
  
- <span data-ttu-id="6a58a-110">때 디버거 연결을 포함 하는 프로세스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a58a-110">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="6a58a-111">이 경우 런타임은 생성 되며 디스패치를 [ICorDebugManagedCallback2::CreateConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md) 이벤트 및 `ChangeConnection` 프로세스의 각 연결에 대 한 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="6a58a-111">In this case, the runtime will generate and dispatch a [ICorDebugManagedCallback2::CreateConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md) event and a `ChangeConnection` event for each connection in the process.</span></span> <span data-ttu-id="6a58a-112">`ChangeConnection` 이벤트가 생성 된 후 해당 연결의 작업 집합이 변경 되었는지 여부에 관계 없이 모든 기존 연결에 대해 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a58a-112">A `ChangeConnection` event is generated for every existing connection, regardless of whether that connection’s set of tasks has been changed since its creation.</span></span>  
  
- <span data-ttu-id="6a58a-113">호스트를 호출 하는 경우 [iclrdebugmanager:: Setconnectiontasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md) 에 [호스팅 API](../../../../docs/framework/unmanaged-api/hosting/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6a58a-113">When a host calls [ICLRDebugManager::SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
 <span data-ttu-id="6a58a-114">디버거는 새 변경 내용을 선택 하는 프로세스의 모든 스레드를 검색 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a58a-114">The debugger should scan all threads in the process to pick up the new changes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a58a-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6a58a-115">Requirements</span></span>  
 <span data-ttu-id="6a58a-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6a58a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a58a-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6a58a-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6a58a-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a58a-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a58a-119">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a58a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a58a-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="6a58a-120">See also</span></span>

- [<span data-ttu-id="6a58a-121">ICorDebugManagedCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6a58a-121">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="6a58a-122">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6a58a-122">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
