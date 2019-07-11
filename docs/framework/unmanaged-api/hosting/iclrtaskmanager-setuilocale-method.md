---
title: ICLRTaskManager::SetUILocale 메서드
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.SetUILocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::SetUILocale
helpviewer_keywords:
- ICLRTaskManager::SetUILocale method [.NET Framework hosting]
- SetUILocale method, ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: 03adaa9a-2beb-49b3-b2c4-6b4fc3f10715
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 101bcac4ad25a0e1c0a5971aad639b0fb05378b6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779961"
---
# <a name="iclrtaskmanagersetuilocale-method"></a><span data-ttu-id="02495-102">ICLRTaskManager::SetUILocale 메서드</span><span class="sxs-lookup"><span data-stu-id="02495-102">ICLRTaskManager::SetUILocale Method</span></span>
<span data-ttu-id="02495-103">현재 실행 중인 작업에는 CLR (공용 언어 런타임을) 사용자 인터페이스 (UI) 로캘 또는 문화권에 호스트가 수정에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="02495-103">Notifies the common language runtime (CLR) that the host has modified the user interface (UI) locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02495-104">구문</span><span class="sxs-lookup"><span data-stu-id="02495-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02495-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="02495-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="02495-106">[in] 새로 할당 된 지리적 문화권 및 사용자 인터페이스 언어에 매핑하는 로캘 식별자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="02495-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language for the user interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="02495-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="02495-107">Return Value</span></span>  
  
|<span data-ttu-id="02495-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="02495-108">HRESULT</span></span>|<span data-ttu-id="02495-109">Description</span><span class="sxs-lookup"><span data-stu-id="02495-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="02495-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="02495-110">S_OK</span></span>|<span data-ttu-id="02495-111">`SetUILocale` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="02495-111">`SetUILocale` returned successfully.</span></span>|  
|<span data-ttu-id="02495-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="02495-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="02495-113">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="02495-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="02495-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="02495-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="02495-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="02495-115">The call timed out.</span></span>|  
|<span data-ttu-id="02495-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="02495-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="02495-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02495-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="02495-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="02495-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="02495-119">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02495-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="02495-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="02495-120">E_FAIL</span></span>|<span data-ttu-id="02495-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="02495-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="02495-122">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="02495-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="02495-123">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="02495-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02495-124">설명</span><span class="sxs-lookup"><span data-stu-id="02495-124">Remarks</span></span>  
 <span data-ttu-id="02495-125">`SetUILocale` 호스트가 로캘 동기화를 위한 메커니즘을 가질 수 있습니다 실행 하는 데 사용할 수 있는 기회를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="02495-125">`SetUILocale` provides an opportunity for the host to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02495-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="02495-126">Requirements</span></span>  
 <span data-ttu-id="02495-127">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="02495-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02495-128">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="02495-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="02495-129">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="02495-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="02495-130">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02495-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02495-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="02495-131">See also</span></span>

- [<span data-ttu-id="02495-132">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="02495-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="02495-133">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="02495-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="02495-134">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="02495-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="02495-135">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="02495-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
