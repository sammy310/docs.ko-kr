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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 50a92058e8a394b95c690d19f1bafdddbed8246a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59135995"
---
# <a name="icorconfigurationsetgchostcontrol-method"></a><span data-ttu-id="7aa00-102">ICorConfiguration::SetGCHostControl 메서드</span><span class="sxs-lookup"><span data-stu-id="7aa00-102">ICorConfiguration::SetGCHostControl Method</span></span>
<span data-ttu-id="7aa00-103">가비지 수집기에 의해 가상 메모리의 한계를 변경 하도록 호스트에 요청에 사용할 콜백 인터페이스를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa00-103">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7aa00-104">구문</span><span class="sxs-lookup"><span data-stu-id="7aa00-104">Syntax</span></span>  
  
```  
HRESULT SetGCHostControl (  
    [in] IGCHostControl* pGCHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7aa00-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7aa00-105">Parameters</span></span>  
 `pGCHostControl`  
 <span data-ttu-id="7aa00-106">[in] 에 대 한 포인터를 [IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md) 가비지 수집기가 호스트의 가상 메모리 한계를 변경 하려면 요청할 수 있는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="7aa00-106">[in] A pointer to an [IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md) object that allows the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7aa00-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7aa00-107">Requirements</span></span>  
 <span data-ttu-id="7aa00-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7aa00-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7aa00-109">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7aa00-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7aa00-110">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="7aa00-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7aa00-111">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7aa00-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7aa00-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="7aa00-112">See also</span></span>

- [<span data-ttu-id="7aa00-113">ICorConfiguration 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7aa00-113">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
