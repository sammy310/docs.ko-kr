---
title: ICLRRuntimeHost::UnloadAppDomain 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.UnloadAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::UnloadAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::UnloadAppDomain method [.NET Framework hosting]
- UnloadAppDomain method [.NET Framework hosting]
ms.assetid: 571912bc-3429-4ff8-8eb2-ea993ffbd901
topic_type:
- apiref
ms.openlocfilehash: 2a6dc878f156d5d18970fed72c9722bab60f9ba8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120403"
---
# <a name="iclrruntimehostunloadappdomain-method"></a><span data-ttu-id="47637-102">ICLRRuntimeHost::UnloadAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="47637-102">ICLRRuntimeHost::UnloadAppDomain Method</span></span>
<span data-ttu-id="47637-103">지정 된 숫자 식별자에 해당 하는 관리 되는 <xref:System.AppDomain>를 언로드합니다.</span><span class="sxs-lookup"><span data-stu-id="47637-103">Unloads the managed <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47637-104">구문</span><span class="sxs-lookup"><span data-stu-id="47637-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadAppDomain(  
    [in] DWORD dwAppDomainId  
    [in] BOOL  fWaitUntilDone  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47637-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="47637-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="47637-106">진행 언로드할 응용 프로그램 도메인의 숫자 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="47637-106">[in] The numeric identifier of the application domain to unload.</span></span>  
  
 `fWaitUntilDone`  
 <span data-ttu-id="47637-107">[in] 응용 프로그램 도메인 언로드를 시도 하기 전에 CLR (공용 언어 런타임)이 응용 프로그램의 현재 스레드 실행이 완료 될 때까지 기다려야 함을 나타내는 `true` 합니다.</span><span class="sxs-lookup"><span data-stu-id="47637-107">[in] `true` to indicate that the common language runtime( CLR) must wait until it has finished executing the application's current thread before attempting to unload the application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="47637-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="47637-108">Return Value</span></span>  
  
|<span data-ttu-id="47637-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="47637-109">HRESULT</span></span>|<span data-ttu-id="47637-110">설명</span><span class="sxs-lookup"><span data-stu-id="47637-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="47637-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="47637-111">S_OK</span></span>|<span data-ttu-id="47637-112">`UnloadAppDomain` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="47637-112">`UnloadAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="47637-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="47637-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="47637-114">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47637-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="47637-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="47637-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="47637-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="47637-116">The call timed out.</span></span>|  
|<span data-ttu-id="47637-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="47637-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="47637-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47637-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="47637-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="47637-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="47637-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="47637-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="47637-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="47637-121">E_FAIL</span></span>|<span data-ttu-id="47637-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="47637-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="47637-123">메서드가 E_FAIL을 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="47637-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="47637-124">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="47637-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="47637-125">주의</span><span class="sxs-lookup"><span data-stu-id="47637-125">Remarks</span></span>  
 <span data-ttu-id="47637-126">[GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)를 호출 하 여 현재 스레드가 실행 중인 응용 프로그램 도메인의 숫자 식별자를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47637-126">You can get the numeric identifier of the application domain in which the current thread is executing by calling [GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span> <span data-ttu-id="47637-127">이 식별자는 관리 되는 <xref:System.AppDomain> 형식의 <xref:System.AppDomain.Id%2A> 속성에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="47637-127">This identifier corresponds to the <xref:System.AppDomain.Id%2A> property of the managed <xref:System.AppDomain> type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47637-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="47637-128">Requirements</span></span>  
 <span data-ttu-id="47637-129">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="47637-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47637-130">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="47637-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="47637-131">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47637-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="47637-132">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47637-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47637-133">참조</span><span class="sxs-lookup"><span data-stu-id="47637-133">See also</span></span>

- [<span data-ttu-id="47637-134">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="47637-134">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
