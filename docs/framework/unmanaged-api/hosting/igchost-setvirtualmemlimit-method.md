---
title: IGCHost::SetVirtualMemLimit 메서드
ms.date: 03/30/2017
api_name:
- IGCHost.SetVirtualMemLimit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetVirtualMemLimit
helpviewer_keywords:
- IGCHost::SetVirtualMemLimit method [.NET Framework hosting]
- SetVirtualMemLimit method [.NET Framework hosting]
ms.assetid: c7e7c2d0-e58c-4650-b40c-47b2be2cda45
topic_type:
- apiref
ms.openlocfilehash: c060e4883335a8318970b5fbd74bf72c9e13f5bf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134869"
---
# <a name="igchostsetvirtualmemlimit-method"></a><span data-ttu-id="dba77-102">IGCHost::SetVirtualMemLimit 메서드</span><span class="sxs-lookup"><span data-stu-id="dba77-102">IGCHost::SetVirtualMemLimit Method</span></span>
<span data-ttu-id="dba77-103">런타임 가상 메모리의 최대 크기를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dba77-103">Sets the maximum size of the runtime's virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dba77-104">구문</span><span class="sxs-lookup"><span data-stu-id="dba77-104">Syntax</span></span>  
  
```cpp  
HRESULT SetVirtualMemLimit (  
    [in] SIZE_T sztMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dba77-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dba77-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="dba77-106">진행 런타임 가상 메모리의 최대 크기 (메가바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="dba77-106">[in] The maximum size, in megabytes, of the runtime's virtual memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dba77-107">주의</span><span class="sxs-lookup"><span data-stu-id="dba77-107">Remarks</span></span>  
 <span data-ttu-id="dba77-108">런타임의 가상 메모리의 최대 크기를 동적으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dba77-108">The maximum size of the runtime's virtual memory can be changed dynamically.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dba77-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dba77-109">Requirements</span></span>  
 <span data-ttu-id="dba77-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dba77-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dba77-111">**헤더:** GCHost, GCHost</span><span class="sxs-lookup"><span data-stu-id="dba77-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="dba77-112">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dba77-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dba77-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dba77-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dba77-114">참조</span><span class="sxs-lookup"><span data-stu-id="dba77-114">See also</span></span>

- [<span data-ttu-id="dba77-115">IGCHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dba77-115">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
