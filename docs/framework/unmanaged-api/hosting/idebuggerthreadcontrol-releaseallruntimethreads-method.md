---
title: IDebuggerThreadControl::ReleaseAllRuntimeThreads 메서드
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.ReleaseAllRuntimeThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ReleaseAllRuntimeThreads
helpviewer_keywords:
- ReleaseAllRuntimeThreads method [.NET Framework hosting]
- IDebuggerThreadControl::ReleaseAllRuntimeThreads method [.NET Framework hosting]
ms.assetid: 1a2995ff-5f02-4b49-84dc-3a5f9cfd7d55
topic_type:
- apiref
ms.openlocfilehash: 490648ab8883b1dba257b82c0d0fa3c8e4783814
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684163"
---
# <a name="idebuggerthreadcontrolreleaseallruntimethreads-method"></a><span data-ttu-id="3fe31-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="3fe31-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads Method</span></span>

<span data-ttu-id="3fe31-103">디버깅 서비스가 차단 된 모든 스레드를 해제 하려고 한다는 사실을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="3fe31-103">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fe31-104">구문</span><span class="sxs-lookup"><span data-stu-id="3fe31-104">Syntax</span></span>  
  
```cpp  
HRESULT ReleaseAllRuntimeThreads ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="3fe31-105">설명</span><span class="sxs-lookup"><span data-stu-id="3fe31-105">Remarks</span></span>  

 <span data-ttu-id="3fe31-106">`ReleaseAllRuntimeThreads`메서드는 런타임 스레드에서 호출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3fe31-106">The `ReleaseAllRuntimeThreads` method will never be called on a runtime thread.</span></span> <span data-ttu-id="3fe31-107">호스트에 차단 된 런타임 스레드가 있으면 지금 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fe31-107">If the host has a runtime thread blocked, it should release it now.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fe31-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3fe31-108">Requirements</span></span>  

 <span data-ttu-id="3fe31-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3fe31-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fe31-110">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="3fe31-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3fe31-111">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fe31-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3fe31-112">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fe31-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fe31-113">참조</span><span class="sxs-lookup"><span data-stu-id="3fe31-113">See also</span></span>

- [<span data-ttu-id="3fe31-114">IDebuggerThreadControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3fe31-114">IDebuggerThreadControl Interface</span></span>](idebuggerthreadcontrol-interface.md)
