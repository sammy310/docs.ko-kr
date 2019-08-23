---
title: IHostIoCompletionManager::Bind 메서드
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.Bind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::Bind
helpviewer_keywords:
- IHostIoCompletionManager::Bind method [.NET Framework hosting]
- Bind method [.NET Framework hosting]
ms.assetid: acd74cb5-7e22-4a07-83c3-82288e1abd9f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de39de96cd7c7ba0be2dc1bea78f79cfe996575c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937562"
---
# <a name="ihostiocompletionmanagerbind-method"></a><span data-ttu-id="7d498-102">IHostIoCompletionManager::Bind 메서드</span><span class="sxs-lookup"><span data-stu-id="7d498-102">IHostIoCompletionManager::Bind Method</span></span>
<span data-ttu-id="7d498-103">[Createio완성도 포트](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)에 대 한 이전 호출에 의해 만들어진 i/o 완료 포트에 지정 된 핸들을 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="7d498-103">Binds the specified handle to an I/O completion port that has been created by an earlier call to [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d498-104">구문</span><span class="sxs-lookup"><span data-stu-id="7d498-104">Syntax</span></span>  
  
```cpp  
HRESULT Bind (  
    [in] HANDLE hPort,  
    [in] HANDLE hHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d498-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7d498-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="7d498-106">진행 바인딩할 `hHandle`i/o 완료 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="7d498-106">[in] The I/O completion port to which to bind `hHandle`.</span></span> <span data-ttu-id="7d498-107">의 `hPort` 값이 `hHandle` null 인 경우는 기본 i/o 완료 포트에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d498-107">If the value of `hPort` is null, `hHandle` is bound to the default I/O completion port.</span></span>  
  
 `hHandle`  
 <span data-ttu-id="7d498-108">진행 바인딩할 운영 체제 핸들 `hPort`입니다.</span><span class="sxs-lookup"><span data-stu-id="7d498-108">[in] The operating system handle to bind to `hPort`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7d498-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="7d498-109">Return Value</span></span>  
  
|<span data-ttu-id="7d498-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7d498-110">HRESULT</span></span>|<span data-ttu-id="7d498-111">Description</span><span class="sxs-lookup"><span data-stu-id="7d498-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7d498-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="7d498-112">S_OK</span></span>|<span data-ttu-id="7d498-113">`Bind`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7d498-113">`Bind` returned successfully.</span></span>|  
|<span data-ttu-id="7d498-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7d498-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7d498-115">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d498-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7d498-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7d498-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7d498-117">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7d498-117">The call timed out.</span></span>|  
|<span data-ttu-id="7d498-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7d498-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7d498-119">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d498-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7d498-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7d498-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7d498-121">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7d498-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7d498-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7d498-122">E_FAIL</span></span>|<span data-ttu-id="7d498-123">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7d498-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7d498-124">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7d498-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7d498-125">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d498-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d498-126">설명</span><span class="sxs-lookup"><span data-stu-id="7d498-126">Remarks</span></span>  
 <span data-ttu-id="7d498-127">I/o 완료 포트는를 `CreateIoCompletionPort`호출 하 여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7d498-127">An I/O completion port is created by using a call to `CreateIoCompletionPort`.</span></span> <span data-ttu-id="7d498-128">CLR은를 `Bind` 호출 하 여 핸들을 해당 포트에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="7d498-128">The CLR calls `Bind` to bind a handle to that port.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7d498-129">I/o 요청이 완료 되 면 호스트는 [IclrioOnComplete manager::](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d498-129">When an I/O request completes, the host must call the [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d498-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7d498-130">Requirements</span></span>  
 <span data-ttu-id="7d498-131">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7d498-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d498-132">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7d498-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7d498-133">**라이브러리** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d498-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7d498-134">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d498-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d498-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="7d498-135">See also</span></span>

- [<span data-ttu-id="7d498-136">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7d498-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
