---
description: '자세히 알아보기: ICorDebugManagedCallback2:: ChangeConnection 메서드'
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
ms.openlocfilehash: 854ea7f40cad9bce613b4034afe7688f4aaf4e52
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790921"
---
# <a name="icordebugmanagedcallback2changeconnection-method"></a><span data-ttu-id="e1a10-103">ICorDebugManagedCallback2::ChangeConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="e1a10-103">ICorDebugManagedCallback2::ChangeConnection Method</span></span>

<span data-ttu-id="e1a10-104">지정 된 연결과 관련 된 작업 집합이 변경 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="e1a10-104">Notifies the debugger that the set of tasks associated with the specified connection has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1a10-105">구문</span><span class="sxs-lookup"><span data-stu-id="e1a10-105">Syntax</span></span>  
  
```cpp  
HRESULT ChangeConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1a10-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e1a10-106">Parameters</span></span>  

 `pProcess`  
 <span data-ttu-id="e1a10-107">진행 변경 된 연결을 포함 하는 프로세스를 나타내는 "ICorDebugProcess" 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e1a10-107">[in] A pointer to an "ICorDebugProcess" object that represents the process containing the connection that changed.</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="e1a10-108">진행 변경 된 연결의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e1a10-108">[in] The ID of the connection that changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e1a10-109">설명</span><span class="sxs-lookup"><span data-stu-id="e1a10-109">Remarks</span></span>  

 <span data-ttu-id="e1a10-110">`ChangeConnection`콜백은 다음 중 한 가지 경우에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1a10-110">A `ChangeConnection` callback will be fired in either of the following cases:</span></span>  
  
- <span data-ttu-id="e1a10-111">디버거가 연결을 포함 하는 프로세스에 연결 하는 경우</span><span class="sxs-lookup"><span data-stu-id="e1a10-111">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="e1a10-112">이 경우 런타임은 프로세스의 각 연결에 대해 [ICorDebugManagedCallback2:: CreateConnection](icordebugmanagedcallback2-createconnection-method.md) 이벤트와 이벤트를 생성 하 고 디스패치합니다 `ChangeConnection` .</span><span class="sxs-lookup"><span data-stu-id="e1a10-112">In this case, the runtime will generate and dispatch a [ICorDebugManagedCallback2::CreateConnection](icordebugmanagedcallback2-createconnection-method.md) event and a `ChangeConnection` event for each connection in the process.</span></span> <span data-ttu-id="e1a10-113">`ChangeConnection`연결의 태스크 집합이 생성 된 후 변경 되었는지 여부에 관계 없이 모든 기존 연결에 대해 이벤트가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1a10-113">A `ChangeConnection` event is generated for every existing connection, regardless of whether that connection’s set of tasks has been changed since its creation.</span></span>  
  
- <span data-ttu-id="e1a10-114">호스트가 [호스팅 API](../hosting/index.md)에서 [ICLRDebugManager:: setconnectiontasks](../hosting/iclrdebugmanager-setconnectiontasks-method.md) 를 호출 하는 경우</span><span class="sxs-lookup"><span data-stu-id="e1a10-114">When a host calls [ICLRDebugManager::SetConnectionTasks](../hosting/iclrdebugmanager-setconnectiontasks-method.md) in the [Hosting API](../hosting/index.md).</span></span>  
  
 <span data-ttu-id="e1a10-115">디버거는 프로세스의 모든 스레드를 검색 하 여 새 변경 내용을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1a10-115">The debugger should scan all threads in the process to pick up the new changes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1a10-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e1a10-116">Requirements</span></span>  

 <span data-ttu-id="e1a10-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e1a10-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1a10-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e1a10-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1a10-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1a10-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1a10-120">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1a10-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1a10-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e1a10-121">See also</span></span>

- [<span data-ttu-id="e1a10-122">ICorDebugManagedCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e1a10-122">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="e1a10-123">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e1a10-123">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
