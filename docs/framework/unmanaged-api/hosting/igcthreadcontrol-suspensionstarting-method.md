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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7cb58593a30b855c9fabf55a6ca0a50886dc371f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779481"
---
# <a name="igcthreadcontrolsuspensionstarting-method"></a><span data-ttu-id="2dc1d-102">IGCThreadControl::SuspensionStarting 메서드</span><span class="sxs-lookup"><span data-stu-id="2dc1d-102">IGCThreadControl::SuspensionStarting Method</span></span>
<span data-ttu-id="2dc1d-103">가비지 수집 스레드 일시 중단 또는 다른 일시 중단 런타임에서 시작 되었음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="2dc1d-103">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2dc1d-104">구문</span><span class="sxs-lookup"><span data-stu-id="2dc1d-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionStarting ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="2dc1d-105">설명</span><span class="sxs-lookup"><span data-stu-id="2dc1d-105">Remarks</span></span>  
 <span data-ttu-id="2dc1d-106">하는 동안 스레드 일정을 재조정 하지 마십시오는 `SuspensionStarting` 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dc1d-106">Do not reschedule any threads during the `SuspensionStarting` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2dc1d-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2dc1d-107">Requirements</span></span>  
 <span data-ttu-id="2dc1d-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2dc1d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2dc1d-109">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2dc1d-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2dc1d-110">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="2dc1d-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2dc1d-111">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2dc1d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dc1d-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="2dc1d-112">See also</span></span>

- [<span data-ttu-id="2dc1d-113">IGCThreadControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2dc1d-113">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
