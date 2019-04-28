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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 47ff178cc9ab798593848e56fc7bba8ac82ae295
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61699697"
---
# <a name="idebuggerthreadcontrolthreadisblockingfordebugger-method"></a><span data-ttu-id="401b4-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger 메서드</span><span class="sxs-lookup"><span data-stu-id="401b4-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger Method</span></span>
<span data-ttu-id="401b4-103">이 콜백은 보내는 스레드가 호스트에 알리는 디버깅 서비스 내에서 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="401b4-103">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="401b4-104">구문</span><span class="sxs-lookup"><span data-stu-id="401b4-104">Syntax</span></span>  
  
```  
HRESULT ThreadIsBlockingForDebugger ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="401b4-105">설명</span><span class="sxs-lookup"><span data-stu-id="401b4-105">Remarks</span></span>  
 <span data-ttu-id="401b4-106">`ThreadIsBlockingForDebugger` 메서드는 항상 런타임 스레드에서 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="401b4-106">The `ThreadIsBlockingForDebugger` method will always be called on a runtime thread.</span></span>  
  
 <span data-ttu-id="401b4-107">`ThreadIsBlockingForDebugger` 메서드 사용 하면 호스트가 해당 스레드는 차단 하는 동안 다른 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="401b4-107">The `ThreadIsBlockingForDebugger` method gives the host an opportunity to perform another action while the thread blocks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="401b4-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="401b4-108">Requirements</span></span>  
 <span data-ttu-id="401b4-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="401b4-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="401b4-110">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="401b4-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="401b4-111">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="401b4-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="401b4-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="401b4-112">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="401b4-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="401b4-113">See also</span></span>

- [<span data-ttu-id="401b4-114">IDebuggerThreadControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="401b4-114">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
