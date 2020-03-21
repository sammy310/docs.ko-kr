---
title: IHostSecurityManager::OpenThreadToken 메서드
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.OpenThreadToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::OpenThreadToken
helpviewer_keywords:
- IHostSecurityManager::OpenThreadToken method [.NET Framework hosting]
- OpenThreadToken method [.NET Framework hosting]
ms.assetid: d5999052-8bf0-4a9e-8621-da6284406b18
topic_type:
- apiref
ms.openlocfilehash: 11d042ea9eecc8d428761da6eaa15f7c2907ebd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176268"
---
# <a name="ihostsecuritymanageropenthreadtoken-method"></a><span data-ttu-id="9d409-102">IHostSecurityManager::OpenThreadToken 메서드</span><span class="sxs-lookup"><span data-stu-id="9d409-102">IHostSecurityManager::OpenThreadToken Method</span></span>
<span data-ttu-id="9d409-103">현재 실행 중인 스레드와 연결된 임의 액세스 토큰을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9d409-103">Opens the discretionary access token associated with the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d409-104">구문</span><span class="sxs-lookup"><span data-stu-id="9d409-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenThreadToken (  
    [in]  DWORD    dwDesiredAccess,
    [in]  BOOL     bOpenAsSelf,
    [out] HANDLE   *phThreadToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d409-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9d409-105">Parameters</span></span>  
 `dwDesiredAccess`  
 <span data-ttu-id="9d409-106">【인】 스레드 토큰에 대한 요청된 액세스 유형을 지정하는 액세스 값의 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="9d409-106">[in] A mask of access values that specify the requested types of access to the thread token.</span></span> <span data-ttu-id="9d409-107">이러한 값은 Win32 `OpenThreadToken` 함수에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d409-107">These values are defined in the Win32 `OpenThreadToken` function.</span></span> <span data-ttu-id="9d409-108">요청된 액세스 형식은 토큰의 임의 액세스 제어 목록(DACL)과 조정되어 부여 또는 거부에 대한 액세스 유형을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="9d409-108">The requested access types are reconciled against the token's discretionary access control list (DACL) to determine which types of access to grant or deny.</span></span>  
  
 `bOpenAsSelf`  
 <span data-ttu-id="9d409-109">【인】 `true` 호출 스레드에 대한 프로세스의 보안 컨텍스트를 사용하여 액세스 검사를 수행해야 하도록 지정합니다. `false` 을 사용하 여 호출 스레드 자체에 대 한 보안 컨텍스트를 사용 하 여 액세스 검사를 수행 해야 합니다 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d409-109">[in] `true` to specify that the access check should be made using the security context of the process for the calling thread; `false` to specify that the access check should be performed using the security context for the calling thread itself.</span></span> <span data-ttu-id="9d409-110">스레드가 클라이언트를 가장하는 경우 보안 컨텍스트는 클라이언트 프로세스의 컨텍스트일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d409-110">If the thread is impersonating a client, the security context can be that of a client process.</span></span>  
  
 `phThreadToken`  
 <span data-ttu-id="9d409-111">【아웃】 새로 열린 액세스 토큰에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9d409-111">[out] A pointer to the newly opened access token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9d409-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="9d409-112">Return Value</span></span>  
  
|<span data-ttu-id="9d409-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9d409-113">HRESULT</span></span>|<span data-ttu-id="9d409-114">Description</span><span class="sxs-lookup"><span data-stu-id="9d409-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9d409-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="9d409-115">S_OK</span></span>|<span data-ttu-id="9d409-116">`OpenThreadToken`성공적으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d409-116">`OpenThreadToken` returned successfully.</span></span>|  
|<span data-ttu-id="9d409-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9d409-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9d409-118">공통 언어 런타임(CLR)이 프로세스에 로드되지 않았거나 CLR이 관리 코드를 실행하거나 호출을 성공적으로 처리할 수 없는 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="9d409-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9d409-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9d409-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9d409-120">통화 시간이 시간 미정으로 확인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9d409-120">The call timed out.</span></span>|  
|<span data-ttu-id="9d409-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9d409-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9d409-122">호출자는 잠금을 소유하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d409-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9d409-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9d409-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9d409-124">차단된 스레드 또는 파이버가 대기하는 동안 이벤트가 취소되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9d409-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9d409-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9d409-125">E_FAIL</span></span>|<span data-ttu-id="9d409-126">알 수 없는 치명적인 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="9d409-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9d409-127">메서드가 E_FAIL 반환하면 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9d409-127">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9d409-128">호스팅 메서드에 대한 후속 호출은 HOST_E_CLRNOTAVAILABLE 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9d409-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9d409-129">설명</span><span class="sxs-lookup"><span data-stu-id="9d409-129">Remarks</span></span>  
 <span data-ttu-id="9d409-130">`IHostSecurityManager::OpenThreadToken`Win32 함수를 사용하면 호출자가 임의의 스레드에 핸들을 전달할 수 있지만 호출 스레드와 연결된 토큰만 `IHostSecurityManager::OpenThreadToken` 열린다는 점을 제외하면 동일한 이름의 해당 Win32 함수와 유사하게 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="9d409-130">`IHostSecurityManager::OpenThreadToken` behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::OpenThreadToken` opens only the token associated with the calling thread.</span></span>  
  
 <span data-ttu-id="9d409-131">형식은 `HANDLE` COM을 준수하지 않으며, 즉 크기는 운영 체제에 따라 다르며 사용자 지정 마샬링이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9d409-131">The `HANDLE` type is not COM-compliant, that is, its size is specific to the operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="9d409-132">따라서 이 토큰은 CLR과 호스트 간의 프로세스 내에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d409-132">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d409-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9d409-133">Requirements</span></span>  
 <span data-ttu-id="9d409-134">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9d409-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d409-135">**헤더:** MSCorE.h</span><span class="sxs-lookup"><span data-stu-id="9d409-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9d409-136">**라이브러리:** MSCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="9d409-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9d409-137">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d409-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d409-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9d409-138">See also</span></span>

- [<span data-ttu-id="9d409-139">IHostSecurityContext 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9d409-139">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="9d409-140">IHostSecurityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9d409-140">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
