---
title: IGCThreadControl::SuspensionStarting 메서드
ms.date: 03/30/2017
api_name:
- IGCThreadControl.SuspensionStarting
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SuspensionStarting
helpviewer_keywords:
- IGCThreadControl::SuspensionStarting method [.NET Framework hosting]
- SuspensionStarting method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 0af312af-98e9-415e-b182-42e80a1aee51
topic_type:
- apiref
ms.openlocfilehash: 1e1d63ab28276f69e5b3a762520db8f8300d05bc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134757"
---
# <a name="igcthreadcontrolsuspensionstarting-method"></a><span data-ttu-id="ed667-102">IGCThreadControl::SuspensionStarting 메서드</span><span class="sxs-lookup"><span data-stu-id="ed667-102">IGCThreadControl::SuspensionStarting Method</span></span>
<span data-ttu-id="ed667-103">런타임에서 가비지 수집 또는 기타 일시 중단에 대 한 스레드 일시 중단을 시작 하 고 있음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ed667-103">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed667-104">구문</span><span class="sxs-lookup"><span data-stu-id="ed667-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionStarting ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="ed667-105">주의</span><span class="sxs-lookup"><span data-stu-id="ed667-105">Remarks</span></span>  
 <span data-ttu-id="ed667-106">`SuspensionStarting` 콜백에서는 스레드를 다시 예약 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="ed667-106">Do not reschedule any threads during the `SuspensionStarting` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed667-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ed667-107">Requirements</span></span>  
 <span data-ttu-id="ed667-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed667-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed667-109">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ed667-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ed667-110">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed667-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ed667-111">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed667-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed667-112">참조</span><span class="sxs-lookup"><span data-stu-id="ed667-112">See also</span></span>

- [<span data-ttu-id="ed667-113">IGCThreadControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ed667-113">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
