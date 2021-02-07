---
description: '자세히 알아보기: IHostTaskManager:: GetStackGuarantee Method'
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
ms.openlocfilehash: 6c8bd9839ea0c1fdb72fbbd296061d1a2b6edfe1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753798"
---
# <a name="ihosttaskmanagergetstackguarantee-method"></a><span data-ttu-id="49314-103">IHostTaskManager::GetStackGuarantee 메서드</span><span class="sxs-lookup"><span data-stu-id="49314-103">IHostTaskManager::GetStackGuarantee Method</span></span>

<span data-ttu-id="49314-104">스택 작업이 완료 된 후 프로세스가 종료 되기 전에 사용할 수 있도록 보장 되는 스택 공간의 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="49314-104">Gets the amount of stack space that is guaranteed to be available after a stack operation completes, but before the closing of a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49314-105">구문</span><span class="sxs-lookup"><span data-stu-id="49314-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStackGuarantee(  
    [out] ULONG *pGuarantee  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49314-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="49314-106">Parameters</span></span>  

 `pGuarantee`  
 <span data-ttu-id="49314-107">제한이 사용 가능한 바이트 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="49314-107">[out] A pointer to the number of bytes that are available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49314-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="49314-108">Requirements</span></span>  

 <span data-ttu-id="49314-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="49314-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49314-110">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="49314-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="49314-111">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49314-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="49314-112">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49314-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49314-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="49314-113">See also</span></span>

- [<span data-ttu-id="49314-114">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="49314-114">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
