---
title: IGCHostControl::RequestVirtualMemLimit 메서드
ms.date: 03/30/2017
api_name:
- IGCHostControl.RequestVirtualMemLimit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- RequestVirtualMemLimit
helpviewer_keywords:
- IGCHostControl::RequestVirtualMemLimit method [.NET Framework hosting]
- RequestVirtualMemLimit method [.NET Framework hosting]
ms.assetid: f4984a8c-4c0e-4460-9aa1-d022b3621228
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cbb0b6191c74c2b7ebdc8267701f246c17b016f9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779521"
---
# <a name="igchostcontrolrequestvirtualmemlimit-method"></a><span data-ttu-id="078ae-102">IGCHostControl::RequestVirtualMemLimit 메서드</span><span class="sxs-lookup"><span data-stu-id="078ae-102">IGCHostControl::RequestVirtualMemLimit Method</span></span>
<span data-ttu-id="078ae-103">가상 메모리의 한계를 변경 하려면 호스트를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="078ae-103">Requests the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="078ae-104">구문</span><span class="sxs-lookup"><span data-stu-id="078ae-104">Syntax</span></span>  
  
```cpp  
HRESULT RequestVirtualMemLimit (  
    [in] SIZE_T       sztMaxVirtualMemMB,  
    [in, out] SIZE_T* psztNewMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="078ae-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="078ae-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="078ae-106">[in] 할당할 메모리의 요청 된 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="078ae-106">[in] The requested size of memory to be allocated.</span></span>  
  
 `psztNewMaxVirtualMemMB`  
 <span data-ttu-id="078ae-107">[out에서] 할당 된 메모리의 실제 크기에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="078ae-107">[in, out] A pointer to the actual size of memory allocated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="078ae-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="078ae-108">Requirements</span></span>  
 <span data-ttu-id="078ae-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="078ae-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="078ae-110">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="078ae-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="078ae-111">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="078ae-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="078ae-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="078ae-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="078ae-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="078ae-113">See also</span></span>

- [<span data-ttu-id="078ae-114">IGCHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="078ae-114">IGCHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)
