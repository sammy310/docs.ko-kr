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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2963e2a31fd62470e3ed6933edb38119d286071b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763362"
---
# <a name="iclrtaskmanagergetcurrenttasktype-method"></a><span data-ttu-id="c719d-102">ICLRTaskManager::GetCurrentTaskType 메서드</span><span class="sxs-lookup"><span data-stu-id="c719d-102">ICLRTaskManager::GetCurrentTaskType Method</span></span>
<span data-ttu-id="c719d-103">현재 실행 중인 작업의 형식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c719d-103">Gets the type of the task that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c719d-104">구문</span><span class="sxs-lookup"><span data-stu-id="c719d-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentTaskType(  
    [out] ETaskType *pTaskType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c719d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c719d-105">Parameters</span></span>  
 `pTaskType`  
 <span data-ttu-id="c719d-106">[out] 값에 대 한 포인터를 [ETaskType](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md) 현재 실행 중인 작업의 형식을 나타내는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="c719d-106">[out] A pointer to a value of the [ETaskType](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md) enumeration that indicates the type of task that is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c719d-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c719d-107">Requirements</span></span>  
 <span data-ttu-id="c719d-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c719d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c719d-109">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c719d-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c719d-110">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="c719d-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c719d-111">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c719d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c719d-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="c719d-112">See also</span></span>

- [<span data-ttu-id="c719d-113">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c719d-113">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
