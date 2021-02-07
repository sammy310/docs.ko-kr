---
description: '자세히 알아보기: IDebuggerThreadControl 인터페이스'
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
ms.openlocfilehash: 293a120d44b9b04d7e367546c477fb273f535310
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709772"
---
# <a name="idebuggerthreadcontrol-interface"></a><span data-ttu-id="a28fc-103">IDebuggerThreadControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a28fc-103">IDebuggerThreadControl Interface</span></span>

<span data-ttu-id="a28fc-104">디버깅 서비스에서 스레드의 차단 및 차단 해제에 대해 호스트에 알리는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28fc-104">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a28fc-105">메서드</span><span class="sxs-lookup"><span data-stu-id="a28fc-105">Methods</span></span>  
  
|<span data-ttu-id="a28fc-106">메서드</span><span class="sxs-lookup"><span data-stu-id="a28fc-106">Method</span></span>|<span data-ttu-id="a28fc-107">설명</span><span class="sxs-lookup"><span data-stu-id="a28fc-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a28fc-108">ThreadIsBlockingForDebugger 메서드</span><span class="sxs-lookup"><span data-stu-id="a28fc-108">ThreadIsBlockingForDebugger Method</span></span>](idebuggerthreadcontrol-threadisblockingfordebugger-method.md)|<span data-ttu-id="a28fc-109">이 콜백을 보내는 스레드가 디버깅 서비스 내에서 차단 됨을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="a28fc-109">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>|  
|[<span data-ttu-id="a28fc-110">ReleaseAllRuntimeThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="a28fc-110">ReleaseAllRuntimeThreads Method</span></span>](idebuggerthreadcontrol-releaseallruntimethreads-method.md)|<span data-ttu-id="a28fc-111">디버깅 서비스가 차단 된 모든 스레드를 해제 하려고 한다는 사실을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="a28fc-111">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>|  
|[<span data-ttu-id="a28fc-112">StartBlockingForDebugger 메서드</span><span class="sxs-lookup"><span data-stu-id="a28fc-112">StartBlockingForDebugger Method</span></span>](idebuggerthreadcontrol-startblockingfordebugger-method.md)|<span data-ttu-id="a28fc-113">디버깅 서비스가 모든 스레드를 차단 하기 시작 했음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="a28fc-113">Notifies the host that the debugging services are about to start blocking all threads.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a28fc-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a28fc-114">Requirements</span></span>  

 <span data-ttu-id="a28fc-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a28fc-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a28fc-116">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a28fc-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a28fc-117">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a28fc-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a28fc-118">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a28fc-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a28fc-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a28fc-119">See also</span></span>

- [<span data-ttu-id="a28fc-120">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a28fc-120">Hosting Interfaces</span></span>](hosting-interfaces.md)
