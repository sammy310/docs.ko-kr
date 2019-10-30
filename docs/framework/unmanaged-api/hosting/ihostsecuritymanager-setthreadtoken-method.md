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
ms.openlocfilehash: aa17f637ef71373697db5ce66e4a6540c5cc5fbd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139487"
---
# <a name="ihostsecuritymanagersetthreadtoken-method"></a><span data-ttu-id="e195d-102">IHostSecurityManager::SetThreadToken 메서드</span><span class="sxs-lookup"><span data-stu-id="e195d-102">IHostSecurityManager::SetThreadToken Method</span></span>
<span data-ttu-id="e195d-103">현재 실행 중인 스레드에 대 한 핸들을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e195d-103">Sets a handle for the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e195d-104">구문</span><span class="sxs-lookup"><span data-stu-id="e195d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadToken (  
    [in] HANDLE hToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e195d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e195d-105">Parameters</span></span>  
 `hToken`  
 <span data-ttu-id="e195d-106">진행 현재 실행 중인 스레드에 대해 설정할 토큰에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="e195d-106">[in] A handle to the token to set for the currently executing thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e195d-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="e195d-107">Return Value</span></span>  
  
|<span data-ttu-id="e195d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e195d-108">HRESULT</span></span>|<span data-ttu-id="e195d-109">설명</span><span class="sxs-lookup"><span data-stu-id="e195d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e195d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e195d-110">S_OK</span></span>|<span data-ttu-id="e195d-111">`SetThreadToken` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e195d-111">`SetThreadToken` returned successfully.</span></span>|  
|<span data-ttu-id="e195d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e195d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e195d-113">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e195d-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e195d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e195d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e195d-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e195d-115">The call timed out.</span></span>|  
|<span data-ttu-id="e195d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e195d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e195d-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e195d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e195d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e195d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e195d-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e195d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e195d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e195d-120">E_FAIL</span></span>|<span data-ttu-id="e195d-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e195d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e195d-122">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e195d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e195d-123">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e195d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e195d-124">주의</span><span class="sxs-lookup"><span data-stu-id="e195d-124">Remarks</span></span>  
 <span data-ttu-id="e195d-125">`IHostSecurityManager::SetThreadToken`는 Win32 함수를 사용 하 여 호출자가 임의의 스레드에 대 한 핸들을 전달할 수 있는 반면, `IHostSecurityManager::SetThreadToken`는 토큰을 현재 실행 중인 스레드에만 연결할 수 있다는 점만 제외 하면 동일한 이름의 해당 Win32 함수와 비슷하게 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="e195d-125">`IHostSecurityManager::SetThreadToken` behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::SetThreadToken` can associate a token only with the currently executing thread.</span></span>  
  
 <span data-ttu-id="e195d-126">`HANDLE` 형식이 COM 규격이 아닙니다. 즉, 크기는 운영 체제에 따라 달라 지 며 사용자 지정 마샬링이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e195d-126">The `HANDLE` type is not COM-compliant; that is, its size is specific to an operating system and it requires custom marshaling.</span></span> <span data-ttu-id="e195d-127">따라서이 토큰은 프로세스 내 에서만 사용 되 고 CLR과 호스트 사이에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e195d-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e195d-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e195d-128">Requirements</span></span>  
 <span data-ttu-id="e195d-129">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e195d-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e195d-130">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e195d-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e195d-131">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e195d-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e195d-132">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e195d-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e195d-133">참조</span><span class="sxs-lookup"><span data-stu-id="e195d-133">See also</span></span>

- [<span data-ttu-id="e195d-134">IHostSecurityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e195d-134">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="e195d-135">IHostThreadPoolManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e195d-135">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
