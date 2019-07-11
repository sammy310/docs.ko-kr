---
title: IHostSecurityManager::SetThreadToken 메서드
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.SetThreadToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::SetThreadToken
helpviewer_keywords:
- SetThreadToken method [.NET Framework hosting]
- IHostSecurityManager::SetThreadToken method [.NET Framework hosting]
ms.assetid: e951c345-8a86-4587-911b-a1a57bc6428a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3aabc21eb15479fe81c922c3fe9625b210caa9d2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778007"
---
# <a name="ihostsecuritymanagersetthreadtoken-method"></a><span data-ttu-id="8b67a-102">IHostSecurityManager::SetThreadToken 메서드</span><span class="sxs-lookup"><span data-stu-id="8b67a-102">IHostSecurityManager::SetThreadToken Method</span></span>
<span data-ttu-id="8b67a-103">현재 실행 중인 스레드에 대 한 핸들을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8b67a-103">Sets a handle for the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b67a-104">구문</span><span class="sxs-lookup"><span data-stu-id="8b67a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadToken (  
    [in] HANDLE hToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b67a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8b67a-105">Parameters</span></span>  
 `hToken`  
 <span data-ttu-id="8b67a-106">[in] 현재 실행 중인 스레드에 대 한 설정 하는 토큰 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="8b67a-106">[in] A handle to the token to set for the currently executing thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8b67a-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="8b67a-107">Return Value</span></span>  
  
|<span data-ttu-id="8b67a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8b67a-108">HRESULT</span></span>|<span data-ttu-id="8b67a-109">설명</span><span class="sxs-lookup"><span data-stu-id="8b67a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8b67a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8b67a-110">S_OK</span></span>|<span data-ttu-id="8b67a-111">`SetThreadToken` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b67a-111">`SetThreadToken` returned successfully.</span></span>|  
|<span data-ttu-id="8b67a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8b67a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8b67a-113">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8b67a-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8b67a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8b67a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8b67a-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8b67a-115">The call timed out.</span></span>|  
|<span data-ttu-id="8b67a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8b67a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8b67a-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b67a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8b67a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8b67a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8b67a-119">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b67a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8b67a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8b67a-120">E_FAIL</span></span>|<span data-ttu-id="8b67a-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8b67a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8b67a-122">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8b67a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8b67a-123">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b67a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8b67a-124">설명</span><span class="sxs-lookup"><span data-stu-id="8b67a-124">Remarks</span></span>  
 <span data-ttu-id="8b67a-125">`IHostSecurityManager::SetThreadToken` 동작 마찬가지로 동일한 이름의 해당 Win32 함수를 제외 하 고 Win32 함수에서는 호출자가 임의의 스레드 핸들을 전달 하는 동안 요소를 `IHostSecurityManager::SetThreadToken` 만 현재 실행 중인 스레드를 사용 하 여 토큰을 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b67a-125">`IHostSecurityManager::SetThreadToken` behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::SetThreadToken` can associate a token only with the currently executing thread.</span></span>  
  
 <span data-ttu-id="8b67a-126">`HANDLE` 형식을 COM 규격이 아닙니다. 즉, 크기로 운영 체제에 따라 다릅니다 하 고 사용자 지정 마샬링 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b67a-126">The `HANDLE` type is not COM-compliant; that is, its size is specific to an operating system and it requires custom marshaling.</span></span> <span data-ttu-id="8b67a-127">따라서이 토큰은 CLR과 호스트 간의 프로세스 내 에서만 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b67a-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b67a-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8b67a-128">Requirements</span></span>  
 <span data-ttu-id="8b67a-129">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8b67a-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b67a-130">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8b67a-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8b67a-131">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="8b67a-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8b67a-132">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b67a-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b67a-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="8b67a-133">See also</span></span>

- [<span data-ttu-id="8b67a-134">IHostSecurityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8b67a-134">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="8b67a-135">IHostThreadPoolManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8b67a-135">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
