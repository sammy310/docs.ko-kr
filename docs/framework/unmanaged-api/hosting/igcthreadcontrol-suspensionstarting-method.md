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
ms.openlocfilehash: 7613bc744ad4c2e172fc4f6dd7bf282fb3d9072c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59179753"
---
# <a name="igcthreadcontrolsuspensionstarting-method"></a><span data-ttu-id="71946-102">IGCThreadControl::SuspensionStarting 메서드</span><span class="sxs-lookup"><span data-stu-id="71946-102">IGCThreadControl::SuspensionStarting Method</span></span>
<span data-ttu-id="71946-103">가비지 수집 스레드 일시 중단 또는 다른 일시 중단 런타임에서 시작 되었음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="71946-103">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71946-104">구문</span><span class="sxs-lookup"><span data-stu-id="71946-104">Syntax</span></span>  
  
```  
HRESULT SuspensionStarting ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="71946-105">설명</span><span class="sxs-lookup"><span data-stu-id="71946-105">Remarks</span></span>  
 <span data-ttu-id="71946-106">하는 동안 스레드 일정을 재조정 하지 마십시오는 `SuspensionStarting` 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="71946-106">Do not reschedule any threads during the `SuspensionStarting` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71946-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="71946-107">Requirements</span></span>  
 <span data-ttu-id="71946-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="71946-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71946-109">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="71946-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="71946-110">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="71946-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="71946-111">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="71946-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="71946-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="71946-112">See also</span></span>

- [<span data-ttu-id="71946-113">IGCThreadControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="71946-113">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
