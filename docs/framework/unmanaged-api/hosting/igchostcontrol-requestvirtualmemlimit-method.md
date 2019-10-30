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
ms.openlocfilehash: ccff575974093de0bf00b257cba78c509f9cbd92
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134769"
---
# <a name="igchostcontrolrequestvirtualmemlimit-method"></a><span data-ttu-id="2fff1-102">IGCHostControl::RequestVirtualMemLimit 메서드</span><span class="sxs-lookup"><span data-stu-id="2fff1-102">IGCHostControl::RequestVirtualMemLimit Method</span></span>
<span data-ttu-id="2fff1-103">가상 메모리의 한도를 변경 하도록 호스트에 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fff1-103">Requests the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fff1-104">구문</span><span class="sxs-lookup"><span data-stu-id="2fff1-104">Syntax</span></span>  
  
```cpp  
HRESULT RequestVirtualMemLimit (  
    [in] SIZE_T       sztMaxVirtualMemMB,  
    [in, out] SIZE_T* psztNewMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2fff1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2fff1-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="2fff1-106">진행 할당 될 요청 된 메모리 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="2fff1-106">[in] The requested size of memory to be allocated.</span></span>  
  
 `psztNewMaxVirtualMemMB`  
 <span data-ttu-id="2fff1-107">[in, out] 할당 된 메모리의 실제 크기에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2fff1-107">[in, out] A pointer to the actual size of memory allocated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fff1-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2fff1-108">Requirements</span></span>  
 <span data-ttu-id="2fff1-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2fff1-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fff1-110">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2fff1-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2fff1-111">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fff1-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2fff1-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fff1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fff1-113">참조</span><span class="sxs-lookup"><span data-stu-id="2fff1-113">See also</span></span>

- [<span data-ttu-id="2fff1-114">IGCHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2fff1-114">IGCHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)
