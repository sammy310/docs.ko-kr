---
title: IHostIoCompletionManager::CloseIoCompletionPort 메서드
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.CloseIoCompletionPort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::CloseIoCompletionPort
helpviewer_keywords:
- IHostIoCompletionManager::CloseIoCompletionPort method [.NET Framework hosting]
- CloseIoCompletionPort method [.NET Framework hosting]
ms.assetid: e86ad7be-3758-498a-a972-5522d69dfbb3
topic_type:
- apiref
ms.openlocfilehash: 254254af705f93793b030882e0ac79d0372ca55f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133886"
---
# <a name="ihostiocompletionmanagercloseiocompletionport-method"></a><span data-ttu-id="e724c-102">IHostIoCompletionManager::CloseIoCompletionPort 메서드</span><span class="sxs-lookup"><span data-stu-id="e724c-102">IHostIoCompletionManager::CloseIoCompletionPort Method</span></span>
<span data-ttu-id="e724c-103">호스트에서 [Createio이상 포트](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)에 대 한 이전 호출을 통해 열린 포트를 닫도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="e724c-103">Requests that the host close a port that was opened through an earlier call to [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e724c-104">구문</span><span class="sxs-lookup"><span data-stu-id="e724c-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseIoCompletionPort (  
    [in] HANDLE hPort  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e724c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e724c-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="e724c-106">진행 닫을 포트의 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="e724c-106">[in] The handle of the port to close.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e724c-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="e724c-107">Return Value</span></span>  
  
|<span data-ttu-id="e724c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e724c-108">HRESULT</span></span>|<span data-ttu-id="e724c-109">설명</span><span class="sxs-lookup"><span data-stu-id="e724c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e724c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e724c-110">S_OK</span></span>|<span data-ttu-id="e724c-111">`CloseIoCompletionPort` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e724c-111">`CloseIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="e724c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e724c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e724c-113">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e724c-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e724c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e724c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e724c-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e724c-115">The call timed out.</span></span>|  
|<span data-ttu-id="e724c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e724c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e724c-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e724c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e724c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e724c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e724c-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e724c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e724c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e724c-120">E_FAIL</span></span>|<span data-ttu-id="e724c-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e724c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e724c-122">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e724c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e724c-123">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e724c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e724c-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="e724c-124">E_INVALIDARG</span></span>|<span data-ttu-id="e724c-125">잘못 된 포트 핸들이 전달 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e724c-125">An invalid port handle was passed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e724c-126">주의</span><span class="sxs-lookup"><span data-stu-id="e724c-126">Remarks</span></span>  
 <span data-ttu-id="e724c-127">`hPort`는 `CreateIoCompletionPort`에 대 한 이전 호출에 의해 생성 된 포트에 대 한 핸들 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e724c-127">`hPort` must be a handle to a port that was created by an earlier call to `CreateIoCompletionPort`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e724c-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e724c-128">Requirements</span></span>  
 <span data-ttu-id="e724c-129">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e724c-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e724c-130">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e724c-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e724c-131">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e724c-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e724c-132">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e724c-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e724c-133">참조</span><span class="sxs-lookup"><span data-stu-id="e724c-133">See also</span></span>

- [<span data-ttu-id="e724c-134">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e724c-134">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="e724c-135">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e724c-135">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
