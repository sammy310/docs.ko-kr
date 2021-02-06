---
description: '자세히 알아보기: ICLRRuntimeHost:: UnloadAppDomain 메서드'
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
ms.openlocfilehash: 2a47c6250434c3ee4122f8eeae75f25ee4c08a34
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637289"
---
# <a name="iclrruntimehostunloadappdomain-method"></a><span data-ttu-id="17378-103">ICLRRuntimeHost::UnloadAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="17378-103">ICLRRuntimeHost::UnloadAppDomain Method</span></span>

<span data-ttu-id="17378-104"><xref:System.AppDomain>지정 된 숫자 식별자에 해당 하는 관리 되는를 언로드합니다.</span><span class="sxs-lookup"><span data-stu-id="17378-104">Unloads the managed <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17378-105">구문</span><span class="sxs-lookup"><span data-stu-id="17378-105">Syntax</span></span>  
  
```cpp  
HRESULT UnloadAppDomain(  
    [in] DWORD dwAppDomainId  
    [in] BOOL  fWaitUntilDone  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17378-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="17378-106">Parameters</span></span>  

 `dwAppDomainId`  
 <span data-ttu-id="17378-107">진행 언로드할 응용 프로그램 도메인의 숫자 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="17378-107">[in] The numeric identifier of the application domain to unload.</span></span>  
  
 `fWaitUntilDone`  
 <span data-ttu-id="17378-108">[in] `true` 응용 프로그램 도메인 언로드를 시도 하기 전에 CLR (공용 언어 런타임)이 응용 프로그램의 현재 스레드 실행이 완료 될 때까지 대기 해야 함을 나타내려면입니다.</span><span class="sxs-lookup"><span data-stu-id="17378-108">[in] `true` to indicate that the common language runtime( CLR) must wait until it has finished executing the application's current thread before attempting to unload the application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="17378-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="17378-109">Return Value</span></span>  
  
|<span data-ttu-id="17378-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="17378-110">HRESULT</span></span>|<span data-ttu-id="17378-111">설명</span><span class="sxs-lookup"><span data-stu-id="17378-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="17378-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="17378-112">S_OK</span></span>|<span data-ttu-id="17378-113">`UnloadAppDomain` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="17378-113">`UnloadAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="17378-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="17378-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="17378-115">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17378-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="17378-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="17378-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="17378-117">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="17378-117">The call timed out.</span></span>|  
|<span data-ttu-id="17378-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="17378-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="17378-119">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="17378-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="17378-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="17378-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="17378-121">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="17378-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="17378-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="17378-122">E_FAIL</span></span>|<span data-ttu-id="17378-123">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="17378-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="17378-124">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="17378-124">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="17378-125">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="17378-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17378-126">설명</span><span class="sxs-lookup"><span data-stu-id="17378-126">Remarks</span></span>  

 <span data-ttu-id="17378-127">[GetCurrentAppDomainId](iclrruntimehost-getcurrentappdomainid-method.md)를 호출 하 여 현재 스레드가 실행 중인 응용 프로그램 도메인의 숫자 식별자를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17378-127">You can get the numeric identifier of the application domain in which the current thread is executing by calling [GetCurrentAppDomainId](iclrruntimehost-getcurrentappdomainid-method.md).</span></span> <span data-ttu-id="17378-128">이 식별자는 <xref:System.AppDomain.Id%2A> 관리 되는 형식의 속성에 해당 <xref:System.AppDomain> 합니다.</span><span class="sxs-lookup"><span data-stu-id="17378-128">This identifier corresponds to the <xref:System.AppDomain.Id%2A> property of the managed <xref:System.AppDomain> type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17378-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="17378-129">Requirements</span></span>  

 <span data-ttu-id="17378-130">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="17378-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17378-131">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="17378-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="17378-132">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="17378-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="17378-133">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17378-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17378-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="17378-134">See also</span></span>

- [<span data-ttu-id="17378-135">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="17378-135">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
