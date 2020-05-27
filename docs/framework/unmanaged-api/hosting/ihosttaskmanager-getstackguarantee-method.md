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
ms.openlocfilehash: d76242eb8539f2e8dffbf39b7eaf595664bdce8e
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842025"
---
# <a name="ihosttaskmanagergetstackguarantee-method"></a><span data-ttu-id="322fe-102">IHostTaskManager::GetStackGuarantee 메서드</span><span class="sxs-lookup"><span data-stu-id="322fe-102">IHostTaskManager::GetStackGuarantee Method</span></span>
<span data-ttu-id="322fe-103">스택 작업이 완료 된 후 프로세스가 종료 되기 전에 사용할 수 있도록 보장 되는 스택 공간의 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="322fe-103">Gets the amount of stack space that is guaranteed to be available after a stack operation completes, but before the closing of a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="322fe-104">구문</span><span class="sxs-lookup"><span data-stu-id="322fe-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackGuarantee(  
    [out] ULONG *pGuarantee  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="322fe-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="322fe-105">Parameters</span></span>  
 `pGuarantee`  
 <span data-ttu-id="322fe-106">제한이 사용 가능한 바이트 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="322fe-106">[out] A pointer to the number of bytes that are available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="322fe-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="322fe-107">Requirements</span></span>  
 <span data-ttu-id="322fe-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="322fe-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="322fe-109">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="322fe-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="322fe-110">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="322fe-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="322fe-111">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="322fe-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="322fe-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="322fe-112">See also</span></span>

- [<span data-ttu-id="322fe-113">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="322fe-113">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
