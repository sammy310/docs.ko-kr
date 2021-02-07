---
description: '자세히 알아보기: IHostSecurityManager:: RevertToSelf 메서드'
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
ms.openlocfilehash: f3488653bcb498c7521de0e368b33bc444967f21
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671505"
---
# <a name="ihostsecuritymanagerreverttoself-method"></a><span data-ttu-id="6d699-103">IHostSecurityManager::RevertToSelf 메서드</span><span class="sxs-lookup"><span data-stu-id="6d699-103">IHostSecurityManager::RevertToSelf Method</span></span>

<span data-ttu-id="6d699-104">현재 사용자 id의 가장을 종료 하 고 원래 스레드 토큰을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d699-104">Terminates impersonation of the current user identity and returns the original thread token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d699-105">구문</span><span class="sxs-lookup"><span data-stu-id="6d699-105">Syntax</span></span>  
  
```cpp  
HRESULT RevertToSelf ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="6d699-106">Return Value</span><span class="sxs-lookup"><span data-stu-id="6d699-106">Return Value</span></span>  
  
|<span data-ttu-id="6d699-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6d699-107">HRESULT</span></span>|<span data-ttu-id="6d699-108">설명</span><span class="sxs-lookup"><span data-stu-id="6d699-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6d699-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="6d699-109">S_OK</span></span>|<span data-ttu-id="6d699-110">`RevertToSelf` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6d699-110">`RevertToSelf` returned successfully.</span></span>|  
|<span data-ttu-id="6d699-111">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6d699-111">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6d699-112">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d699-112">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6d699-113">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6d699-113">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6d699-114">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6d699-114">The call timed out.</span></span>|  
|<span data-ttu-id="6d699-115">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6d699-115">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6d699-116">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d699-116">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6d699-117">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6d699-117">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6d699-118">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6d699-118">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6d699-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6d699-119">E_FAIL</span></span>|<span data-ttu-id="6d699-120">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6d699-120">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6d699-121">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6d699-121">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6d699-122">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d699-122">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d699-123">설명</span><span class="sxs-lookup"><span data-stu-id="6d699-123">Remarks</span></span>  

 <span data-ttu-id="6d699-124">`RevertToSelf`[ImpersonateLoggedOnUser](ihostsecuritymanager-impersonateloggedonuser-method.md) 메서드를 이전에 호출 하 고 나 서 원래 스레드 토큰을 반환 하기 위해가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d699-124">`RevertToSelf` is called to return to the original thread token, after an earlier call to the [ImpersonateLoggedOnUser](ihostsecuritymanager-impersonateloggedonuser-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d699-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6d699-125">Requirements</span></span>  

 <span data-ttu-id="6d699-126">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6d699-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d699-127">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="6d699-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6d699-128">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d699-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6d699-129">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d699-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d699-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6d699-130">See also</span></span>

- [<span data-ttu-id="6d699-131">IHostSecurityContext 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6d699-131">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="6d699-132">IHostSecurityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6d699-132">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="6d699-133">ImpersonateLoggedOnUser 메서드</span><span class="sxs-lookup"><span data-stu-id="6d699-133">ImpersonateLoggedOnUser Method</span></span>](ihostsecuritymanager-impersonateloggedonuser-method.md)
