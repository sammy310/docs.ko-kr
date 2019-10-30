---
title: IHostTask::Start 메서드
ms.date: 03/30/2017
api_name:
- IHostTask.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Start
helpviewer_keywords:
- IHostTask::Start method [.NET Framework hosting]
- Start method, IHostTask interface [.NET Framework hosting]
ms.assetid: b18742b0-d8c4-401c-ae89-e6eccdaa81d0
topic_type:
- apiref
ms.openlocfilehash: fe93a3bab267ccca941974b734c86329ad0f4d03
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121344"
---
# <a name="ihosttaskstart-method"></a><span data-ttu-id="d230f-102">IHostTask::Start 메서드</span><span class="sxs-lookup"><span data-stu-id="d230f-102">IHostTask::Start Method</span></span>
<span data-ttu-id="d230f-103">호스트가 현재 [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) 인스턴스로 표시 된 작업을 일시 중단에서 라이브 상태로 이동 하 여 코드를 실행할 수 있도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="d230f-103">Requests that the host move the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance from a suspended to a live state, in which code can be executed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d230f-104">구문</span><span class="sxs-lookup"><span data-stu-id="d230f-104">Syntax</span></span>  
  
```cpp  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="d230f-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="d230f-105">Return Value</span></span>  
  
|<span data-ttu-id="d230f-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d230f-106">HRESULT</span></span>|<span data-ttu-id="d230f-107">설명</span><span class="sxs-lookup"><span data-stu-id="d230f-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d230f-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="d230f-108">S_OK</span></span>|<span data-ttu-id="d230f-109">시작이 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d230f-109">Start returned successfully.</span></span>|  
|<span data-ttu-id="d230f-110">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d230f-110">E_FAIL</span></span>|<span data-ttu-id="d230f-111">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d230f-111">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d230f-112">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 CLR (공용 언어 런타임)을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d230f-112">When a method returns E_FAIL, the common language runtime (CLR) is no longer usable within the process.</span></span> <span data-ttu-id="d230f-113">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d230f-113">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d230f-114">주의</span><span class="sxs-lookup"><span data-stu-id="d230f-114">Remarks</span></span>  
 <span data-ttu-id="d230f-115">`Start`는 치명적인 오류가 발생 한 경우를 제외 하 고는 항상 HRESULT 값 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d230f-115">`Start` always returns an HRESULT value of S_OK, except in cases where a catastrophic failure has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d230f-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d230f-116">Requirements</span></span>  
 <span data-ttu-id="d230f-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d230f-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d230f-118">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d230f-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d230f-119">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d230f-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d230f-120">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d230f-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d230f-121">참조</span><span class="sxs-lookup"><span data-stu-id="d230f-121">See also</span></span>

- [<span data-ttu-id="d230f-122">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d230f-122">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="d230f-123">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d230f-123">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="d230f-124">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d230f-124">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="d230f-125">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d230f-125">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
