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
ms.openlocfilehash: 5a2b2e5560c292598f0110de9445eb66ba794997
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683110"
---
# <a name="ihostsecuritymanagersetthreadtoken-method"></a><span data-ttu-id="9e506-102">IHostSecurityManager::SetThreadToken 메서드</span><span class="sxs-lookup"><span data-stu-id="9e506-102">IHostSecurityManager::SetThreadToken Method</span></span>

<span data-ttu-id="9e506-103">현재 실행 중인 스레드에 대 한 핸들을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e506-103">Sets a handle for the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e506-104">구문</span><span class="sxs-lookup"><span data-stu-id="9e506-104">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadToken (  
    [in] HANDLE hToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e506-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9e506-105">Parameters</span></span>  

 `hToken`  
 <span data-ttu-id="9e506-106">진행 현재 실행 중인 스레드에 대해 설정할 토큰에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="9e506-106">[in] A handle to the token to set for the currently executing thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9e506-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="9e506-107">Return Value</span></span>  
  
|<span data-ttu-id="9e506-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9e506-108">HRESULT</span></span>|<span data-ttu-id="9e506-109">설명</span><span class="sxs-lookup"><span data-stu-id="9e506-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9e506-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9e506-110">S_OK</span></span>|<span data-ttu-id="9e506-111">`SetThreadToken` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9e506-111">`SetThreadToken` returned successfully.</span></span>|  
|<span data-ttu-id="9e506-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9e506-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9e506-113">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e506-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9e506-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9e506-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9e506-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9e506-115">The call timed out.</span></span>|  
|<span data-ttu-id="9e506-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9e506-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9e506-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9e506-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9e506-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9e506-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9e506-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9e506-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9e506-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9e506-120">E_FAIL</span></span>|<span data-ttu-id="9e506-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9e506-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9e506-122">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9e506-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9e506-123">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e506-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e506-124">설명</span><span class="sxs-lookup"><span data-stu-id="9e506-124">Remarks</span></span>  

 <span data-ttu-id="9e506-125">`IHostSecurityManager::SetThreadToken` 는 Win32 함수에서 호출자가 임의의 스레드에 대 한 핸들을 전달할 수 있도록 허용 하는 반면,는 `IHostSecurityManager::SetThreadToken` 토큰을 현재 실행 중인 스레드에만 연결할 수 있다는 점만 제외 하면 동일한 이름의 해당 Win32 함수와 비슷하게 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e506-125">`IHostSecurityManager::SetThreadToken` behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::SetThreadToken` can associate a token only with the currently executing thread.</span></span>  
  
 <span data-ttu-id="9e506-126">`HANDLE`형식이 COM 규격이 아닙니다. 즉, 해당 크기는 운영 체제에 따라 달라 지 며 사용자 지정 마샬링이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e506-126">The `HANDLE` type is not COM-compliant; that is, its size is specific to an operating system and it requires custom marshaling.</span></span> <span data-ttu-id="9e506-127">따라서이 토큰은 프로세스 내 에서만 사용 되 고 CLR과 호스트 사이에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e506-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e506-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9e506-128">Requirements</span></span>  

 <span data-ttu-id="9e506-129">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9e506-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e506-130">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9e506-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9e506-131">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e506-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9e506-132">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e506-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e506-133">참조</span><span class="sxs-lookup"><span data-stu-id="9e506-133">See also</span></span>

- [<span data-ttu-id="9e506-134">IHostSecurityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9e506-134">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="9e506-135">IHostThreadPoolManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9e506-135">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
