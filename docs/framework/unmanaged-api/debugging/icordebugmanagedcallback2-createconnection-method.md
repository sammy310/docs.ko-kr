---
title: ICorDebugManagedCallback2::CreateConnection 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.CreateConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::CreateConnection
helpviewer_keywords:
- CreateConnection method [.NET Framework debugging]
- ICorDebugManagedCallback2::CreateConnection method [.NET Framework debugging]
ms.assetid: 49e647be-9d63-4250-9d11-704e2a400d1b
topic_type:
- apiref
ms.openlocfilehash: 5a4ebf65dfaaa487e87f3fd78e54c468c7e24a89
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697248"
---
# <a name="icordebugmanagedcallback2createconnection-method"></a><span data-ttu-id="35463-102">ICorDebugManagedCallback2::CreateConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="35463-102">ICorDebugManagedCallback2::CreateConnection Method</span></span>

<span data-ttu-id="35463-103">새 연결이 생성 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="35463-103">Notifies the debugger that a new connection has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35463-104">구문</span><span class="sxs-lookup"><span data-stu-id="35463-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId,  
    [in] WCHAR                *pConnName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35463-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="35463-105">Parameters</span></span>  

 `pProcess`  
 <span data-ttu-id="35463-106">진행 연결이 생성 된 프로세스를 나타내는 "ICorDebugProcess" 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="35463-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the connection was created</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="35463-107">진행 새 연결의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="35463-107">[in] The ID of the new connection.</span></span>  
  
 `pConnName`  
 <span data-ttu-id="35463-108">진행 새 연결의 이름에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="35463-108">[in] A pointer to the name of the new connection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35463-109">설명</span><span class="sxs-lookup"><span data-stu-id="35463-109">Remarks</span></span>  

 <span data-ttu-id="35463-110">`CreateConnection`콜백은 다음 중 한 가지 경우에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="35463-110">A `CreateConnection` callback will be fired in either of the following cases:</span></span>  
  
- <span data-ttu-id="35463-111">디버거가 연결을 포함 하는 프로세스에 연결 하는 경우</span><span class="sxs-lookup"><span data-stu-id="35463-111">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="35463-112">이 경우 런타임은 `CreateConnection` 프로세스의 각 연결에 대해 이벤트 및 [ICorDebugManagedCallback2:: ChangeConnection](icordebugmanagedcallback2-changeconnection-method.md) 이벤트를 생성 하 고 디스패치합니다.</span><span class="sxs-lookup"><span data-stu-id="35463-112">In this case, the runtime will generate and dispatch a `CreateConnection` event and a [ICorDebugManagedCallback2::ChangeConnection](icordebugmanagedcallback2-changeconnection-method.md) event for each connection in the process.</span></span>  
  
- <span data-ttu-id="35463-113">호스트가 [호스팅 API](../hosting/index.md)에서 [ICLRDebugManager:: beginconnection](../hosting/iclrdebugmanager-beginconnection-method.md) 을 호출 하는 경우</span><span class="sxs-lookup"><span data-stu-id="35463-113">When a host calls [ICLRDebugManager::BeginConnection](../hosting/iclrdebugmanager-beginconnection-method.md) in the [Hosting API](../hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35463-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="35463-114">Requirements</span></span>  

 <span data-ttu-id="35463-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="35463-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35463-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="35463-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="35463-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35463-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35463-118">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35463-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35463-119">참조</span><span class="sxs-lookup"><span data-stu-id="35463-119">See also</span></span>

- [<span data-ttu-id="35463-120">ICorDebugManagedCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="35463-120">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="35463-121">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="35463-121">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
