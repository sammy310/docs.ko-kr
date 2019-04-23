---
title: IHostSecurityManager::RevertToSelf 메서드
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.RevertToSelf
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::RevertToSelf
helpviewer_keywords:
- RevertToSelf method [.NET Framework hosting]
- IHostSecurityManager::RevertToSelf method [.NET Framework hosting]
ms.assetid: 189f28f8-f9a1-4192-aedc-91084e4f8b99
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d282f6d37a2be8a41f4fbda579b3b467b9bfc8ca
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59120070"
---
# <a name="ihostsecuritymanagerreverttoself-method"></a><span data-ttu-id="c821a-102">IHostSecurityManager::RevertToSelf 메서드</span><span class="sxs-lookup"><span data-stu-id="c821a-102">IHostSecurityManager::RevertToSelf Method</span></span>
<span data-ttu-id="c821a-103">현재 사용자 id의 가장을 종료 하 고 원래 스레드 토큰을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c821a-103">Terminates impersonation of the current user identity and returns the original thread token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c821a-104">구문</span><span class="sxs-lookup"><span data-stu-id="c821a-104">Syntax</span></span>  
  
```  
HRESULT RevertToSelf ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="c821a-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="c821a-105">Return Value</span></span>  
  
|<span data-ttu-id="c821a-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c821a-106">HRESULT</span></span>|<span data-ttu-id="c821a-107">설명</span><span class="sxs-lookup"><span data-stu-id="c821a-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c821a-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="c821a-108">S_OK</span></span>|<span data-ttu-id="c821a-109">`RevertToSelf` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c821a-109">`RevertToSelf` returned successfully.</span></span>|  
|<span data-ttu-id="c821a-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c821a-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c821a-111">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c821a-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c821a-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c821a-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c821a-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c821a-113">The call timed out.</span></span>|  
|<span data-ttu-id="c821a-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c821a-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c821a-115">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c821a-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c821a-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c821a-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c821a-117">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c821a-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c821a-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c821a-118">E_FAIL</span></span>|<span data-ttu-id="c821a-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c821a-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c821a-120">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c821a-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c821a-121">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c821a-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c821a-122">설명</span><span class="sxs-lookup"><span data-stu-id="c821a-122">Remarks</span></span>  
 <span data-ttu-id="c821a-123">`RevertToSelf` 호출 되어 원래 스레드 토큰에 대 한 이전 호출 후 반환 된 [ImpersonateLoggedOnUser](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="c821a-123">`RevertToSelf` is called to return to the original thread token, after an earlier call to the [ImpersonateLoggedOnUser](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c821a-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c821a-124">Requirements</span></span>  
 <span data-ttu-id="c821a-125">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c821a-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c821a-126">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c821a-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c821a-127">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="c821a-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c821a-128">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c821a-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c821a-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="c821a-129">See also</span></span>

- [<span data-ttu-id="c821a-130">IHostSecurityContext 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c821a-130">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="c821a-131">IHostSecurityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c821a-131">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="c821a-132">ImpersonateLoggedOnUser 메서드</span><span class="sxs-lookup"><span data-stu-id="c821a-132">ImpersonateLoggedOnUser Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)
