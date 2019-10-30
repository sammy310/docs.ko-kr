---
title: IGCThreadControl::SuspensionEnding 메서드
ms.date: 03/30/2017
api_name:
- IGCThreadControl.SuspensionEnding
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SuspensionEnding
helpviewer_keywords:
- IGCThreadControl::SuspensionEnding method [.NET Framework hosting]
- SuspensionEnding method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 70814265-c734-4ddc-9502-fe8b28d2b414
topic_type:
- apiref
ms.openlocfilehash: 8d8efccde56d8d37a75b1d9bbec706411c6b1f45
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134793"
---
# <a name="igcthreadcontrolsuspensionending-method"></a><span data-ttu-id="43b23-102">IGCThreadControl::SuspensionEnding 메서드</span><span class="sxs-lookup"><span data-stu-id="43b23-102">IGCThreadControl::SuspensionEnding Method</span></span>
<span data-ttu-id="43b23-103">가비지 수집 또는 다른 일시 중단 후 런타임이 스레드를 다시 시작 하 고 있음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="43b23-103">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43b23-104">구문</span><span class="sxs-lookup"><span data-stu-id="43b23-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionEnding (  
    [in] DWORD Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43b23-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="43b23-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="43b23-106">진행 가비지 수집이 수행 된 세대입니다.</span><span class="sxs-lookup"><span data-stu-id="43b23-106">[in] The generation on which a garbage collection has been performed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43b23-107">주의</span><span class="sxs-lookup"><span data-stu-id="43b23-107">Remarks</span></span>  
 <span data-ttu-id="43b23-108">`SuspensionEnding` 콜백에서는 스레드를 다시 예약 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="43b23-108">Do not reschedule any threads during the `SuspensionEnding` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43b23-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="43b23-109">Requirements</span></span>  
 <span data-ttu-id="43b23-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="43b23-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43b23-111">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="43b23-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="43b23-112">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43b23-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="43b23-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43b23-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43b23-114">참조</span><span class="sxs-lookup"><span data-stu-id="43b23-114">See also</span></span>

- [<span data-ttu-id="43b23-115">IGCThreadControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="43b23-115">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
