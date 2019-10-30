---
title: ICLRTaskManager::GetCurrentTaskType 메서드
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.GetCurrentTaskType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::GetCurrentTaskType
helpviewer_keywords:
- GetCurrentTaskType method [.NET Framework hosting]
- ICLRTaskManager::GetCurrentTaskType method [.NET Framework hosting]
ms.assetid: 6b0d9259-dbe2-45bb-b34d-990f60c73424
topic_type:
- apiref
ms.openlocfilehash: 848255d44ce8637182f18288d30151a3f0df0912
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092158"
---
# <a name="iclrtaskmanagergetcurrenttasktype-method"></a><span data-ttu-id="8cfc6-102">ICLRTaskManager::GetCurrentTaskType 메서드</span><span class="sxs-lookup"><span data-stu-id="8cfc6-102">ICLRTaskManager::GetCurrentTaskType Method</span></span>
<span data-ttu-id="8cfc6-103">현재 실행 중인 작업의 형식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8cfc6-103">Gets the type of the task that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cfc6-104">구문</span><span class="sxs-lookup"><span data-stu-id="8cfc6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentTaskType(  
    [out] ETaskType *pTaskType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8cfc6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8cfc6-105">Parameters</span></span>  
 `pTaskType`  
 <span data-ttu-id="8cfc6-106">제한이 현재 실행 중인 작업의 유형을 나타내는 [Etasktype](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md) 열거형의 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8cfc6-106">[out] A pointer to a value of the [ETaskType](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md) enumeration that indicates the type of task that is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8cfc6-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8cfc6-107">Requirements</span></span>  
 <span data-ttu-id="8cfc6-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8cfc6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8cfc6-109">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8cfc6-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8cfc6-110">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cfc6-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8cfc6-111">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8cfc6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cfc6-112">참조</span><span class="sxs-lookup"><span data-stu-id="8cfc6-112">See also</span></span>

- [<span data-ttu-id="8cfc6-113">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8cfc6-113">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
