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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 90b0cba50129bc728089e41ece5a30697cfc3bc5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144419"
---
# <a name="igcthreadcontrolsuspensionending-method"></a><span data-ttu-id="428eb-102">IGCThreadControl::SuspensionEnding 메서드</span><span class="sxs-lookup"><span data-stu-id="428eb-102">IGCThreadControl::SuspensionEnding Method</span></span>
<span data-ttu-id="428eb-103">런타임 스레드를 다시 시작 가비지 수집 또는 기타 일시 중단 한 후 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="428eb-103">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="428eb-104">구문</span><span class="sxs-lookup"><span data-stu-id="428eb-104">Syntax</span></span>  
  
```  
HRESULT SuspensionEnding (  
    [in] DWORD Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="428eb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="428eb-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="428eb-106">[in] 가비지 컬렉션을 수행한 세대입니다.</span><span class="sxs-lookup"><span data-stu-id="428eb-106">[in] The generation on which a garbage collection has been performed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="428eb-107">설명</span><span class="sxs-lookup"><span data-stu-id="428eb-107">Remarks</span></span>  
 <span data-ttu-id="428eb-108">하는 동안 스레드 일정을 재조정 하지 마십시오는 `SuspensionEnding` 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="428eb-108">Do not reschedule any threads during the `SuspensionEnding` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="428eb-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="428eb-109">Requirements</span></span>  
 <span data-ttu-id="428eb-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="428eb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="428eb-111">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="428eb-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="428eb-112">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="428eb-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="428eb-113">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="428eb-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="428eb-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="428eb-114">See also</span></span>

- [<span data-ttu-id="428eb-115">IGCThreadControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="428eb-115">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
