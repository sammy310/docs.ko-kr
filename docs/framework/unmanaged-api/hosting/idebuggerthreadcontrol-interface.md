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
ms.openlocfilehash: 82c6113f4df3334500128df22f7e9ce8d4bf151f
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805284"
---
# <a name="idebuggerthreadcontrol-interface"></a><span data-ttu-id="e71a5-102">IDebuggerThreadControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e71a5-102">IDebuggerThreadControl Interface</span></span>
<span data-ttu-id="e71a5-103">디버깅 서비스에서 스레드의 차단 및 차단 해제에 대해 호스트에 알리는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71a5-103">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e71a5-104">메서드</span><span class="sxs-lookup"><span data-stu-id="e71a5-104">Methods</span></span>  
  
|<span data-ttu-id="e71a5-105">메서드</span><span class="sxs-lookup"><span data-stu-id="e71a5-105">Method</span></span>|<span data-ttu-id="e71a5-106">Description</span><span class="sxs-lookup"><span data-stu-id="e71a5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e71a5-107">ThreadIsBlockingForDebugger 메서드</span><span class="sxs-lookup"><span data-stu-id="e71a5-107">ThreadIsBlockingForDebugger Method</span></span>](idebuggerthreadcontrol-threadisblockingfordebugger-method.md)|<span data-ttu-id="e71a5-108">이 콜백을 보내는 스레드가 디버깅 서비스 내에서 차단 됨을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="e71a5-108">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>|  
|[<span data-ttu-id="e71a5-109">ReleaseAllRuntimeThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="e71a5-109">ReleaseAllRuntimeThreads Method</span></span>](idebuggerthreadcontrol-releaseallruntimethreads-method.md)|<span data-ttu-id="e71a5-110">디버깅 서비스가 차단 된 모든 스레드를 해제 하려고 한다는 사실을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="e71a5-110">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>|  
|[<span data-ttu-id="e71a5-111">StartBlockingForDebugger 메서드</span><span class="sxs-lookup"><span data-stu-id="e71a5-111">StartBlockingForDebugger Method</span></span>](idebuggerthreadcontrol-startblockingfordebugger-method.md)|<span data-ttu-id="e71a5-112">디버깅 서비스가 모든 스레드를 차단 하기 시작 했음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="e71a5-112">Notifies the host that the debugging services are about to start blocking all threads.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e71a5-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e71a5-113">Requirements</span></span>  
 <span data-ttu-id="e71a5-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e71a5-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e71a5-115">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e71a5-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e71a5-116">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e71a5-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e71a5-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e71a5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e71a5-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e71a5-118">See also</span></span>

- [<span data-ttu-id="e71a5-119">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e71a5-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
