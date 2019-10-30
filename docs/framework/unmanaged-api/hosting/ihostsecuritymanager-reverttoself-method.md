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
ms.openlocfilehash: b896c5509cc4862a6416381f89bc04a28959e091
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121462"
---
# <a name="ihostsecuritymanagerreverttoself-method"></a><span data-ttu-id="8c0b4-102">IHostSecurityManager::RevertToSelf 메서드</span><span class="sxs-lookup"><span data-stu-id="8c0b4-102">IHostSecurityManager::RevertToSelf Method</span></span>
<span data-ttu-id="8c0b4-103">현재 사용자 id의 가장을 종료 하 고 원래 스레드 토큰을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c0b4-103">Terminates impersonation of the current user identity and returns the original thread token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c0b4-104">구문</span><span class="sxs-lookup"><span data-stu-id="8c0b4-104">Syntax</span></span>  
  
```cpp  
HRESULT RevertToSelf ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="8c0b4-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="8c0b4-105">Return Value</span></span>  
  
|<span data-ttu-id="8c0b4-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8c0b4-106">HRESULT</span></span>|<span data-ttu-id="8c0b4-107">설명</span><span class="sxs-lookup"><span data-stu-id="8c0b4-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8c0b4-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="8c0b4-108">S_OK</span></span>|<span data-ttu-id="8c0b4-109">`RevertToSelf` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8c0b4-109">`RevertToSelf` returned successfully.</span></span>|  
|<span data-ttu-id="8c0b4-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8c0b4-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8c0b4-111">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c0b4-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8c0b4-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8c0b4-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8c0b4-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8c0b4-113">The call timed out.</span></span>|  
|<span data-ttu-id="8c0b4-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8c0b4-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8c0b4-115">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8c0b4-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8c0b4-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8c0b4-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8c0b4-117">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8c0b4-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8c0b4-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8c0b4-118">E_FAIL</span></span>|<span data-ttu-id="8c0b4-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8c0b4-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8c0b4-120">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8c0b4-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8c0b4-121">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c0b4-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c0b4-122">주의</span><span class="sxs-lookup"><span data-stu-id="8c0b4-122">Remarks</span></span>  
 <span data-ttu-id="8c0b4-123">[ImpersonateLoggedOnUser](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md) 메서드를 이전에 호출 하 고 나면 `RevertToSelf` 호출 되어 원래 스레드 토큰으로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="8c0b4-123">`RevertToSelf` is called to return to the original thread token, after an earlier call to the [ImpersonateLoggedOnUser](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c0b4-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8c0b4-124">Requirements</span></span>  
 <span data-ttu-id="8c0b4-125">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8c0b4-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c0b4-126">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8c0b4-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8c0b4-127">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c0b4-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8c0b4-128">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c0b4-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c0b4-129">참조</span><span class="sxs-lookup"><span data-stu-id="8c0b4-129">See also</span></span>

- [<span data-ttu-id="8c0b4-130">IHostSecurityContext 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8c0b4-130">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="8c0b4-131">IHostSecurityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8c0b4-131">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="8c0b4-132">ImpersonateLoggedOnUser 메서드</span><span class="sxs-lookup"><span data-stu-id="8c0b4-132">ImpersonateLoggedOnUser Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)
