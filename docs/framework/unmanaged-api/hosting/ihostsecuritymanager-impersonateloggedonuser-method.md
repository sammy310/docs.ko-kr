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
ms.openlocfilehash: dd1d1af8072ac11e37bd2eb1a47d76b12685cb31
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724782"
---
# <a name="ihostsecuritymanagerimpersonateloggedonuser-method"></a><span data-ttu-id="3a9db-102">IHostSecurityManager::ImpersonateLoggedOnUser 메서드</span><span class="sxs-lookup"><span data-stu-id="3a9db-102">IHostSecurityManager::ImpersonateLoggedOnUser Method</span></span>

<span data-ttu-id="3a9db-103">현재 사용자 id의 자격 증명을 사용 하 여 코드를 실행 하도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a9db-103">Requests that code be executed using the credentials of the current user identity.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a9db-104">구문</span><span class="sxs-lookup"><span data-stu-id="3a9db-104">Syntax</span></span>  
  
```cpp  
HRESULT ImpersonateLoggedOnUser (  
    [in] HANDLE hToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a9db-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3a9db-105">Parameters</span></span>  

 `hToken`  
 <span data-ttu-id="3a9db-106">진행 가장할 사용자의 자격 증명을 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="3a9db-106">[in] A token representing the credentials of the user to be impersonated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3a9db-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="3a9db-107">Return Value</span></span>  
  
|<span data-ttu-id="3a9db-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3a9db-108">HRESULT</span></span>|<span data-ttu-id="3a9db-109">설명</span><span class="sxs-lookup"><span data-stu-id="3a9db-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3a9db-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3a9db-110">S_OK</span></span>|<span data-ttu-id="3a9db-111">`ImpersonateLoggedOnUser` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3a9db-111">`ImpersonateLoggedOnUser` returned successfully.</span></span>|  
|<span data-ttu-id="3a9db-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3a9db-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3a9db-113">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a9db-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3a9db-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3a9db-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3a9db-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3a9db-115">The call timed out.</span></span>|  
|<span data-ttu-id="3a9db-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3a9db-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3a9db-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3a9db-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3a9db-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3a9db-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3a9db-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3a9db-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3a9db-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3a9db-120">E_FAIL</span></span>|<span data-ttu-id="3a9db-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3a9db-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3a9db-122">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3a9db-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3a9db-123">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a9db-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a9db-124">설명</span><span class="sxs-lookup"><span data-stu-id="3a9db-124">Remarks</span></span>  

 <span data-ttu-id="3a9db-125">`LogonUser`또는 관련 Win32 함수를 호출 하 여 현재 사용자 id의 자격 증명에 대 한 핸들을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3a9db-125">Call `LogonUser` or a related Win32 function to get a handle to the credentials of the current user identity.</span></span>  
  
 <span data-ttu-id="3a9db-126">`HANDLE`형식이 COM 규격이 아닙니다. 즉, 해당 크기는 운영 체제에 따라 달라 지 며 사용자 지정 마샬링이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a9db-126">The `HANDLE` type is not COM-compliant, that is, its size is specific to an operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="3a9db-127">따라서이 토큰은 프로세스 내 에서만 사용 되 고 CLR과 호스트 사이에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a9db-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a9db-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3a9db-128">Requirements</span></span>  

 <span data-ttu-id="3a9db-129">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a9db-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a9db-130">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="3a9db-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3a9db-131">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a9db-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3a9db-132">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a9db-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a9db-133">참조</span><span class="sxs-lookup"><span data-stu-id="3a9db-133">See also</span></span>

- [<span data-ttu-id="3a9db-134">IHostSecurityContext 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3a9db-134">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="3a9db-135">IHostSecurityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3a9db-135">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="3a9db-136">RevertToSelf 메서드</span><span class="sxs-lookup"><span data-stu-id="3a9db-136">RevertToSelf Method</span></span>](ihostsecuritymanager-reverttoself-method.md)
