---
title: IHostSecurityManager::ImpersonateLoggedOnUser 메서드
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.ImpersonateLoggedOnUser
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::ImpersonateLoggedOnUser
helpviewer_keywords:
- ImpersonateLoggedOnUser method [.NET Framework hosting]
- IHostSecurityManager::ImpersonateLoggedOnUser method [.NET Framework hosting]
ms.assetid: acc49ba0-f1d9-45ad-871f-9d053a89dcbe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3e4a90e8cd50ef1b3324aed35ae5cc34225bb2f7
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471357"
---
# <a name="ihostsecuritymanagerimpersonateloggedonuser-method"></a><span data-ttu-id="d1e17-102">IHostSecurityManager::ImpersonateLoggedOnUser 메서드</span><span class="sxs-lookup"><span data-stu-id="d1e17-102">IHostSecurityManager::ImpersonateLoggedOnUser Method</span></span>
<span data-ttu-id="d1e17-103">요청 된 현재 사용자 id의 자격 증명을 사용 하 여 코드를 실행 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e17-103">Requests that code be executed using the credentials of the current user identity.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1e17-104">구문</span><span class="sxs-lookup"><span data-stu-id="d1e17-104">Syntax</span></span>  
  
```  
HRESULT ImpersonateLoggedOnUser (  
    [in] HANDLE hToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1e17-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d1e17-105">Parameters</span></span>  
 `hToken`  
 <span data-ttu-id="d1e17-106">[in] 가장할 사용자의 자격 증명을 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="d1e17-106">[in] A token representing the credentials of the user to be impersonated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d1e17-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="d1e17-107">Return Value</span></span>  
  
|<span data-ttu-id="d1e17-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d1e17-108">HRESULT</span></span>|<span data-ttu-id="d1e17-109">설명</span><span class="sxs-lookup"><span data-stu-id="d1e17-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d1e17-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d1e17-110">S_OK</span></span>|<span data-ttu-id="d1e17-111">`ImpersonateLoggedOnUser` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e17-111">`ImpersonateLoggedOnUser` returned successfully.</span></span>|  
|<span data-ttu-id="d1e17-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d1e17-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d1e17-113">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d1e17-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d1e17-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d1e17-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d1e17-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d1e17-115">The call timed out.</span></span>|  
|<span data-ttu-id="d1e17-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d1e17-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d1e17-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1e17-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d1e17-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d1e17-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d1e17-119">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1e17-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d1e17-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d1e17-120">E_FAIL</span></span>|<span data-ttu-id="d1e17-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d1e17-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d1e17-122">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d1e17-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d1e17-123">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e17-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1e17-124">설명</span><span class="sxs-lookup"><span data-stu-id="d1e17-124">Remarks</span></span>  
 <span data-ttu-id="d1e17-125">호출 `LogonUser` 또는 관련된 Win32 함수를 현재 사용자 id의 자격 증명에 대 한 핸들을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d1e17-125">Call `LogonUser` or a related Win32 function to get a handle to the credentials of the current user identity.</span></span>  
  
 <span data-ttu-id="d1e17-126">`HANDLE` 형식은 COM 규격, 즉, 해당 크기는 운영 체제에 따라 다릅니다 및 사용자 지정 마샬링 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e17-126">The `HANDLE` type is not COM-compliant, that is, its size is specific to an operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="d1e17-127">따라서이 토큰은 CLR과 호스트 간의 프로세스 내 에서만 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e17-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1e17-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d1e17-128">Requirements</span></span>  
 <span data-ttu-id="d1e17-129">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d1e17-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1e17-130">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d1e17-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d1e17-131">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="d1e17-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d1e17-132">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1e17-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1e17-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="d1e17-133">See also</span></span>
- [<span data-ttu-id="d1e17-134">IHostSecurityContext 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1e17-134">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="d1e17-135">IHostSecurityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1e17-135">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="d1e17-136">RevertToSelf 메서드</span><span class="sxs-lookup"><span data-stu-id="d1e17-136">RevertToSelf Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)
