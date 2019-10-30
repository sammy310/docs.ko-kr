---
title: ICorConfiguration::SetGCHostControl 메서드
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetGCHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCHostControl
helpviewer_keywords:
- ICorConfiguration::SetGCHostControl method [.NET Framework hosting]
- SetGCHostControl method [.NET Framework hosting]
ms.assetid: bca6bd79-e288-475a-aa46-6bf81541d966
topic_type:
- apiref
ms.openlocfilehash: 5a32fb0480e76f47495590a29c329f54722e2dee
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127786"
---
# <a name="icorconfigurationsetgchostcontrol-method"></a><span data-ttu-id="016a8-102">ICorConfiguration::SetGCHostControl 메서드</span><span class="sxs-lookup"><span data-stu-id="016a8-102">ICorConfiguration::SetGCHostControl Method</span></span>
<span data-ttu-id="016a8-103">가비지 수집기에서 가상 메모리의 한도를 변경 하는 호스트를 요청 하는 데 사용할 콜백 인터페이스를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="016a8-103">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="016a8-104">구문</span><span class="sxs-lookup"><span data-stu-id="016a8-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCHostControl (  
    [in] IGCHostControl* pGCHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="016a8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="016a8-105">Parameters</span></span>  
 `pGCHostControl`  
 <span data-ttu-id="016a8-106">진행 가비지 수집기가 가상 메모리의 한도를 변경 하도록 호스트를 요청할 수 있도록 하는 [IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md) 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="016a8-106">[in] A pointer to an [IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md) object that allows the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="016a8-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="016a8-107">Requirements</span></span>  
 <span data-ttu-id="016a8-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="016a8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="016a8-109">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="016a8-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="016a8-110">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="016a8-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="016a8-111">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="016a8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="016a8-112">참조</span><span class="sxs-lookup"><span data-stu-id="016a8-112">See also</span></span>

- [<span data-ttu-id="016a8-113">ICorConfiguration 인터페이스</span><span class="sxs-lookup"><span data-stu-id="016a8-113">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
