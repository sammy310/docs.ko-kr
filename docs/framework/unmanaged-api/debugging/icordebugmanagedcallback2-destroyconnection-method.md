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
ms.openlocfilehash: d725cbe89e0631630affb6b0540a7d5f57ab6b89
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720115"
---
# <a name="icordebugmanagedcallback2destroyconnection-method"></a><span data-ttu-id="77309-102">ICorDebugManagedCallback2::DestroyConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="77309-102">ICorDebugManagedCallback2::DestroyConnection Method</span></span>

<span data-ttu-id="77309-103">지정 된 연결이 종료 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="77309-103">Notifies the debugger that the specified connection has been terminated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77309-104">구문</span><span class="sxs-lookup"><span data-stu-id="77309-104">Syntax</span></span>  
  
```cpp  
HRESULT DestroyConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77309-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="77309-105">Parameters</span></span>  

 `pProcess`  
 <span data-ttu-id="77309-106">진행 제거 된 연결을 포함 하는 프로세스를 나타내는 ICorDebugProcess 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="77309-106">[in] A pointer to an ICorDebugProcess object that represents the process containing the connection that was destroyed.</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="77309-107">진행 제거 된 연결의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="77309-107">[in] The ID of the connection that was destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77309-108">설명</span><span class="sxs-lookup"><span data-stu-id="77309-108">Remarks</span></span>  

 <span data-ttu-id="77309-109">`DestroyConnection`호스트에서 [호스팅 API](../hosting/index.md)의 [ICLRDebugManager:: endconnection](../hosting/iclrdebugmanager-endconnection-method.md) 을 호출 하면 콜백이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="77309-109">A `DestroyConnection` callback will be fired when a host calls [ICLRDebugManager::EndConnection](../hosting/iclrdebugmanager-endconnection-method.md) in the [Hosting API](../hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77309-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="77309-110">Requirements</span></span>  

 <span data-ttu-id="77309-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="77309-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77309-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="77309-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="77309-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77309-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77309-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77309-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77309-115">참조</span><span class="sxs-lookup"><span data-stu-id="77309-115">See also</span></span>

- [<span data-ttu-id="77309-116">ICorDebugManagedCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="77309-116">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="77309-117">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="77309-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
