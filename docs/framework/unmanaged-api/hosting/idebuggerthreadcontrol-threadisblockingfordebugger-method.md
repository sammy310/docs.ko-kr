---
title: IDebuggerThreadControl::ThreadIsBlockingForDebugger 메서드
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.ThreadIsBlockingForDebugger
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ThreadIsBlockingForDebugger
helpviewer_keywords:
- ThreadIsBlockingForDebugger method [.NET Framework hosting]
- IDebuggerThreadControl::ThreadIsBlockingForDebugger method [.NET Framework hosting]
ms.assetid: d4d7cb2d-69da-48b3-879a-1a8a68c9bfa8
topic_type:
- apiref
ms.openlocfilehash: 067d4e844055206543e5c7fb409296b0d0a7a549
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134949"
---
# <a name="idebuggerthreadcontrolthreadisblockingfordebugger-method"></a><span data-ttu-id="d2734-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger 메서드</span><span class="sxs-lookup"><span data-stu-id="d2734-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger Method</span></span>
<span data-ttu-id="d2734-103">이 콜백을 보내는 스레드가 디버깅 서비스 내에서 차단 됨을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="d2734-103">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2734-104">구문</span><span class="sxs-lookup"><span data-stu-id="d2734-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadIsBlockingForDebugger ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="d2734-105">주의</span><span class="sxs-lookup"><span data-stu-id="d2734-105">Remarks</span></span>  
 <span data-ttu-id="d2734-106">`ThreadIsBlockingForDebugger` 메서드는 항상 런타임 스레드에서 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2734-106">The `ThreadIsBlockingForDebugger` method will always be called on a runtime thread.</span></span>  
  
 <span data-ttu-id="d2734-107">`ThreadIsBlockingForDebugger` 메서드는 스레드를 차단 하는 동안 호스트에 다른 작업을 수행할 수 있는 기회를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2734-107">The `ThreadIsBlockingForDebugger` method gives the host an opportunity to perform another action while the thread blocks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2734-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d2734-108">Requirements</span></span>  
 <span data-ttu-id="d2734-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d2734-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2734-110">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d2734-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d2734-111">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2734-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d2734-112">**.Net Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2734-112">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2734-113">참조</span><span class="sxs-lookup"><span data-stu-id="d2734-113">See also</span></span>

- [<span data-ttu-id="d2734-114">IDebuggerThreadControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d2734-114">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
