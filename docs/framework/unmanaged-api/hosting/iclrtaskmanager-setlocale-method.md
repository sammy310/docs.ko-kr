---
title: ICLRTaskManager::SetLocale 메서드
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.SetLocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::SetLocale
helpviewer_keywords:
- SetLocale method, ICLRTaskManager interface [.NET Framework hosting]
- ICLRTaskManager::SetLocale method [.NET Framework hosting]
ms.assetid: ed16bb7f-4206-43a8-b9e9-c5737b69e3af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ae097320ad7cd6e7c840122bf3f315812e9b2acd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763349"
---
# <a name="iclrtaskmanagersetlocale-method"></a><span data-ttu-id="5e8c8-102">ICLRTaskManager::SetLocale 메서드</span><span class="sxs-lookup"><span data-stu-id="5e8c8-102">ICLRTaskManager::SetLocale Method</span></span>
<span data-ttu-id="5e8c8-103">호스트가 현재 실행 중인 태스크의 로캘 식별자 (에 매핑되는 지리적 culture 및 언어)의 값을 수정에 CLR (공용 언어 런타임)에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="5e8c8-103">Notifies the common language runtime (CLR) that the host has modified the value of the locale identifier (which maps to the geographical culture and language) on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e8c8-104">구문</span><span class="sxs-lookup"><span data-stu-id="5e8c8-104">Syntax</span></span>  
  
```  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e8c8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5e8c8-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="5e8c8-106">[in] 새로 할당 된 지리적 culture 및 언어에 매핑하는 로캘 식별자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5e8c8-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5e8c8-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="5e8c8-107">Return Value</span></span>  
  
|<span data-ttu-id="5e8c8-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5e8c8-108">HRESULT</span></span>|<span data-ttu-id="5e8c8-109">설명</span><span class="sxs-lookup"><span data-stu-id="5e8c8-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5e8c8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="5e8c8-110">S_OK</span></span>|<span data-ttu-id="5e8c8-111">메서드가 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e8c8-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="5e8c8-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5e8c8-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5e8c8-113">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5e8c8-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5e8c8-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5e8c8-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5e8c8-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5e8c8-115">The call timed out.</span></span>|  
|<span data-ttu-id="5e8c8-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5e8c8-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5e8c8-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5e8c8-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5e8c8-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5e8c8-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5e8c8-119">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e8c8-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5e8c8-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5e8c8-120">E_FAIL</span></span>|<span data-ttu-id="5e8c8-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5e8c8-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5e8c8-122">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5e8c8-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5e8c8-123">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e8c8-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e8c8-124">설명</span><span class="sxs-lookup"><span data-stu-id="5e8c8-124">Remarks</span></span>  
 <span data-ttu-id="5e8c8-125">`SetLocale` 호스트 로캘의 동기화가 있을 수 메커니즘을 실행할 수 있는 기회를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e8c8-125">`SetLocale` gives the host an opportunity to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e8c8-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5e8c8-126">Requirements</span></span>  
 <span data-ttu-id="5e8c8-127">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5e8c8-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e8c8-128">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5e8c8-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5e8c8-129">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="5e8c8-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5e8c8-130">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e8c8-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e8c8-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="5e8c8-131">See also</span></span>

- [<span data-ttu-id="5e8c8-132">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5e8c8-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="5e8c8-133">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5e8c8-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="5e8c8-134">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5e8c8-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="5e8c8-135">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5e8c8-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
