---
title: IHostTaskManager::GetStackGuarantee 메서드
ms.date: 03/30/2017
api_name:
- IHostTaskManager.GetStackGuarantee
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::GetStackGuarantee
helpviewer_keywords:
- GetStackGuarantee method [.NET Framework hosting]
- IHostTaskManager::GetStackGuarantee method [.NET Framework hosting]
ms.assetid: 8176d732-c25c-4520-811d-e3310f339947
topic_type:
- apiref
ms.openlocfilehash: 22ec34c82d0f8e550dfc8941f2c048ebed6cf1d7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133033"
---
# <a name="ihosttaskmanagergetstackguarantee-method"></a><span data-ttu-id="3942f-102">IHostTaskManager::GetStackGuarantee 메서드</span><span class="sxs-lookup"><span data-stu-id="3942f-102">IHostTaskManager::GetStackGuarantee Method</span></span>
<span data-ttu-id="3942f-103">스택 작업이 완료 된 후 프로세스가 종료 되기 전에 사용할 수 있도록 보장 되는 스택 공간의 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3942f-103">Gets the amount of stack space that is guaranteed to be available after a stack operation completes, but before the closing of a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3942f-104">구문</span><span class="sxs-lookup"><span data-stu-id="3942f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackGuarantee(  
    [out] ULONG *pGuarantee  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3942f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3942f-105">Parameters</span></span>  
 `pGuarantee`  
 <span data-ttu-id="3942f-106">제한이 사용 가능한 바이트 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3942f-106">[out] A pointer to the number of bytes that are available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3942f-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3942f-107">Requirements</span></span>  
 <span data-ttu-id="3942f-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3942f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3942f-109">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="3942f-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3942f-110">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3942f-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3942f-111">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3942f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3942f-112">참조</span><span class="sxs-lookup"><span data-stu-id="3942f-112">See also</span></span>

- [<span data-ttu-id="3942f-113">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3942f-113">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
