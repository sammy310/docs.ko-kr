---
title: IDebuggerThreadControl 인터페이스
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IDebuggerThreadControl
helpviewer_keywords:
- IDebuggerThreadControl interface [.NET Framework hosting]
ms.assetid: 0a270c42-a7d1-45f1-a64d-fa3e84d14532
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a551d3cc6ab3dd3887f232018f8201de4036d1b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59096838"
---
# <a name="idebuggerthreadcontrol-interface"></a><span data-ttu-id="fbf9a-102">IDebuggerThreadControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fbf9a-102">IDebuggerThreadControl Interface</span></span>
<span data-ttu-id="fbf9a-103">차단 하는 방법에 대 한 호스트에 알리고 디버깅 서비스에 의해 스레드 차단 해제에 대 한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbf9a-103">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fbf9a-104">메서드</span><span class="sxs-lookup"><span data-stu-id="fbf9a-104">Methods</span></span>  
  
|<span data-ttu-id="fbf9a-105">메서드</span><span class="sxs-lookup"><span data-stu-id="fbf9a-105">Method</span></span>|<span data-ttu-id="fbf9a-106">설명</span><span class="sxs-lookup"><span data-stu-id="fbf9a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fbf9a-107">ThreadIsBlockingForDebugger 메서드</span><span class="sxs-lookup"><span data-stu-id="fbf9a-107">ThreadIsBlockingForDebugger Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-threadisblockingfordebugger-method.md)|<span data-ttu-id="fbf9a-108">이 콜백은 보내는 스레드가 호스트에 알리는 디버깅 서비스 내에서 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="fbf9a-108">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>|  
|[<span data-ttu-id="fbf9a-109">ReleaseAllRuntimeThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="fbf9a-109">ReleaseAllRuntimeThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-releaseallruntimethreads-method.md)|<span data-ttu-id="fbf9a-110">디버깅 서비스 차단 되는 모든 스레드를 해제 하려는 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="fbf9a-110">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>|  
|[<span data-ttu-id="fbf9a-111">StartBlockingForDebugger 메서드</span><span class="sxs-lookup"><span data-stu-id="fbf9a-111">StartBlockingForDebugger Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-startblockingfordebugger-method.md)|<span data-ttu-id="fbf9a-112">디버깅 서비스 시작 모든 스레드를 차단 하려는 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="fbf9a-112">Notifies the host that the debugging services are about to start blocking all threads.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fbf9a-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fbf9a-113">Requirements</span></span>  
 <span data-ttu-id="fbf9a-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fbf9a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbf9a-115">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fbf9a-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fbf9a-116">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="fbf9a-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fbf9a-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fbf9a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbf9a-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="fbf9a-118">See also</span></span>

- [<span data-ttu-id="fbf9a-119">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fbf9a-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
