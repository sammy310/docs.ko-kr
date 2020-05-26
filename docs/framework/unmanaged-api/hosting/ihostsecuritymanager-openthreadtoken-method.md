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
ms.openlocfilehash: 85c7308f794929d753b50f58f69168f67a31cb85
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803884"
---
# <a name="ihostsecuritymanageropenthreadtoken-method"></a><span data-ttu-id="832b1-102">IHostSecurityManager::OpenThreadToken 메서드</span><span class="sxs-lookup"><span data-stu-id="832b1-102">IHostSecurityManager::OpenThreadToken Method</span></span>
<span data-ttu-id="832b1-103">현재 실행 중인 스레드와 연결 된 임의 액세스 토큰을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="832b1-103">Opens the discretionary access token associated with the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="832b1-104">구문</span><span class="sxs-lookup"><span data-stu-id="832b1-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenThreadToken (  
    [in]  DWORD    dwDesiredAccess,
    [in]  BOOL     bOpenAsSelf,
    [out] HANDLE   *phThreadToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="832b1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="832b1-105">Parameters</span></span>  
 `dwDesiredAccess`  
 <span data-ttu-id="832b1-106">진행 스레드 토큰에 대 한 요청 된 액세스 형식을 지정 하는 액세스 값의 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="832b1-106">[in] A mask of access values that specify the requested types of access to the thread token.</span></span> <span data-ttu-id="832b1-107">이러한 값은 Win32 함수에서 정의 됩니다 `OpenThreadToken` .</span><span class="sxs-lookup"><span data-stu-id="832b1-107">These values are defined in the Win32 `OpenThreadToken` function.</span></span> <span data-ttu-id="832b1-108">요청 된 액세스 형식은 토큰의 DACL (임의 액세스 제어 목록)과 비교 하 여 부여 하거나 거부할 액세스 형식을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="832b1-108">The requested access types are reconciled against the token's discretionary access control list (DACL) to determine which types of access to grant or deny.</span></span>  
  
 `bOpenAsSelf`  
 <span data-ttu-id="832b1-109">[in] `true` 호출 스레드에 대 한 프로세스의 보안 컨텍스트를 사용 하 여 액세스 검사를 수행 하도록 지정 하려면이 고, `false`호출 스레드 자체의 보안 컨텍스트를 사용 하 여 액세스 검사를 수행 하도록 지정 하려면입니다.</span><span class="sxs-lookup"><span data-stu-id="832b1-109">[in] `true` to specify that the access check should be made using the security context of the process for the calling thread; `false` to specify that the access check should be performed using the security context for the calling thread itself.</span></span> <span data-ttu-id="832b1-110">스레드가 클라이언트를 가장 하는 경우 보안 컨텍스트는 클라이언트 프로세스의 컨텍스트가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="832b1-110">If the thread is impersonating a client, the security context can be that of a client process.</span></span>  
  
 `phThreadToken`  
 <span data-ttu-id="832b1-111">제한이 새로 열린 액세스 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="832b1-111">[out] A pointer to the newly opened access token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="832b1-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="832b1-112">Return Value</span></span>  
  
|<span data-ttu-id="832b1-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="832b1-113">HRESULT</span></span>|<span data-ttu-id="832b1-114">Description</span><span class="sxs-lookup"><span data-stu-id="832b1-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="832b1-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="832b1-115">S_OK</span></span>|<span data-ttu-id="832b1-116">`OpenThreadToken`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="832b1-116">`OpenThreadToken` returned successfully.</span></span>|  
|<span data-ttu-id="832b1-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="832b1-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="832b1-118">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="832b1-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="832b1-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="832b1-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="832b1-120">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="832b1-120">The call timed out.</span></span>|  
|<span data-ttu-id="832b1-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="832b1-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="832b1-122">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="832b1-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="832b1-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="832b1-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="832b1-124">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="832b1-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="832b1-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="832b1-125">E_FAIL</span></span>|<span data-ttu-id="832b1-126">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="832b1-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="832b1-127">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="832b1-127">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="832b1-128">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="832b1-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="832b1-129">설명</span><span class="sxs-lookup"><span data-stu-id="832b1-129">Remarks</span></span>  
 <span data-ttu-id="832b1-130">`IHostSecurityManager::OpenThreadToken`는 Win32 함수에서 호출자가 임의 스레드에 대 한 핸들을 전달할 수 있도록 하 고,는 호출 스레드와 연결 된 토큰만 여는 것을 제외 하 고는 동일한 이름의 해당 Win32 함수와 비슷하게 동작 합니다 `IHostSecurityManager::OpenThreadToken` .</span><span class="sxs-lookup"><span data-stu-id="832b1-130">`IHostSecurityManager::OpenThreadToken` behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::OpenThreadToken` opens only the token associated with the calling thread.</span></span>  
  
 <span data-ttu-id="832b1-131">`HANDLE`형식이 COM 규격이 아닙니다. 즉, 해당 크기는 운영 체제에 따라 달라 지 며 사용자 지정 마샬링이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="832b1-131">The `HANDLE` type is not COM-compliant, that is, its size is specific to the operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="832b1-132">따라서이 토큰은 프로세스 내 에서만 사용 되 고 CLR과 호스트 사이에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="832b1-132">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="832b1-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="832b1-133">Requirements</span></span>  
 <span data-ttu-id="832b1-134">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="832b1-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="832b1-135">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="832b1-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="832b1-136">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="832b1-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="832b1-137">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="832b1-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="832b1-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="832b1-138">See also</span></span>

- [<span data-ttu-id="832b1-139">IHostSecurityContext 인터페이스</span><span class="sxs-lookup"><span data-stu-id="832b1-139">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="832b1-140">IHostSecurityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="832b1-140">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
