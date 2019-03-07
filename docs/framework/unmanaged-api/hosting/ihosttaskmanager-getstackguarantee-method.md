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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 100bb73356379d2f251513bbbed0cf1e90752ff5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494376"
---
# <a name="ihosttaskmanagergetstackguarantee-method"></a><span data-ttu-id="8921c-102">IHostTaskManager::GetStackGuarantee 메서드</span><span class="sxs-lookup"><span data-stu-id="8921c-102">IHostTaskManager::GetStackGuarantee Method</span></span>
<span data-ttu-id="8921c-103">프로세스의 닫기 전에 있지만 스택 작업이 완료 되 면 사용할 수 있도록 보장 되는 스택 공간의 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8921c-103">Gets the amount of stack space that is guaranteed to be available after a stack operation completes, but before the closing of a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8921c-104">구문</span><span class="sxs-lookup"><span data-stu-id="8921c-104">Syntax</span></span>  
  
```  
HRESULT GetStackGuarantee(  
    [out] ULONG *pGuarantee  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8921c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8921c-105">Parameters</span></span>  
 `pGuarantee`  
 <span data-ttu-id="8921c-106">[out] 사용할 수 있는 바이트 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8921c-106">[out] A pointer to the number of bytes that are available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8921c-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8921c-107">Requirements</span></span>  
 <span data-ttu-id="8921c-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8921c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8921c-109">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8921c-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8921c-110">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="8921c-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8921c-111">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8921c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8921c-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="8921c-112">See also</span></span>
- [<span data-ttu-id="8921c-113">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8921c-113">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
