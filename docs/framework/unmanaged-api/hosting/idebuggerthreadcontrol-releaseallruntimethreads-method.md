---
description: '자세히 알아보기: IDebuggerThreadControl:: ReleaseAllRuntimeThreads 메서드'
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
ms.openlocfilehash: bf551ccc2ae5bde3333dc8e3957099590a494dd3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709776"
---
# <a name="idebuggerthreadcontrolreleaseallruntimethreads-method"></a><span data-ttu-id="90639-103">IDebuggerThreadControl::ReleaseAllRuntimeThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="90639-103">IDebuggerThreadControl::ReleaseAllRuntimeThreads Method</span></span>

<span data-ttu-id="90639-104">디버깅 서비스가 차단 된 모든 스레드를 해제 하려고 한다는 사실을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="90639-104">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90639-105">구문</span><span class="sxs-lookup"><span data-stu-id="90639-105">Syntax</span></span>  
  
```cpp  
HRESULT ReleaseAllRuntimeThreads ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="90639-106">설명</span><span class="sxs-lookup"><span data-stu-id="90639-106">Remarks</span></span>  

 <span data-ttu-id="90639-107">`ReleaseAllRuntimeThreads`메서드는 런타임 스레드에서 호출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="90639-107">The `ReleaseAllRuntimeThreads` method will never be called on a runtime thread.</span></span> <span data-ttu-id="90639-108">호스트에 차단 된 런타임 스레드가 있으면 지금 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="90639-108">If the host has a runtime thread blocked, it should release it now.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90639-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="90639-109">Requirements</span></span>  

 <span data-ttu-id="90639-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="90639-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90639-111">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="90639-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="90639-112">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90639-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="90639-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90639-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90639-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="90639-114">See also</span></span>

- [<span data-ttu-id="90639-115">IDebuggerThreadControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="90639-115">IDebuggerThreadControl Interface</span></span>](idebuggerthreadcontrol-interface.md)
