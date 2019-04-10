---
title: ICLRRuntimeHost::ExecuteInAppDomain 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteInAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteInAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInAppDomain method [.NET Framework hosting]
- ExecuteInAppDomain method [.NET Framework hosting]
ms.assetid: e2b0e2db-3fae-4b56-844e-d30a125a660c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 86348c35a023e22d10c4ad2e08f5cb1104b895a8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165497"
---
# <a name="iclrruntimehostexecuteinappdomain-method"></a><span data-ttu-id="b834e-102">ICLRRuntimeHost::ExecuteInAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="b834e-102">ICLRRuntimeHost::ExecuteInAppDomain Method</span></span>
<span data-ttu-id="b834e-103">지정 된 <xref:System.AppDomain> 지정 된 관리 되는 코드를 실행 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="b834e-103">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b834e-104">구문</span><span class="sxs-lookup"><span data-stu-id="b834e-104">Syntax</span></span>  
  
```  
HRESULT ExecuteInAppDomain(  
    [in] DWORD AppDomainId,   
    [in] FExecuteInDomainCallback pCallback,   
    [in] void* cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b834e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b834e-105">Parameters</span></span>  
 `AppDomainId`  
 <span data-ttu-id="b834e-106">[in] 숫자 ID를 <xref:System.AppDomain> 지정 된 메서드를 실행 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="b834e-106">[in] The numeric ID of the <xref:System.AppDomain> in which to execute the specified method.</span></span>  
  
 `pCallback`  
 <span data-ttu-id="b834e-107">[in] 지정 된 내에서 실행 하는 함수에 대 한 포인터 <xref:System.AppDomain>합니다.</span><span class="sxs-lookup"><span data-stu-id="b834e-107">[in] A pointer to the function to execute within the specified <xref:System.AppDomain>.</span></span>  
  
 `cookie`  
 <span data-ttu-id="b834e-108">[in] 불투명 호출자에 게 할당 된 메모리에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b834e-108">[in] A pointer to opaque caller-allocated memory.</span></span> <span data-ttu-id="b834e-109">이 매개 변수는 CLR (공용 언어 런타임)에서 도메인 콜백에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b834e-109">This parameter is passed by the common language runtime (CLR) to the domain callback.</span></span> <span data-ttu-id="b834e-110">런타임에서 관리 되는 힙 메모리; 아닙니다. 할당 및 수명이 메모리는 호출자에 의해 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b834e-110">It is not runtime-managed heap memory; both the allocation and lifetime of this memory are controlled by the caller.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b834e-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="b834e-111">Return Value</span></span>  
  
|<span data-ttu-id="b834e-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b834e-112">HRESULT</span></span>|<span data-ttu-id="b834e-113">설명</span><span class="sxs-lookup"><span data-stu-id="b834e-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b834e-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="b834e-114">S_OK</span></span>|`ExecuteInAppDomain` <span data-ttu-id="b834e-115">성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b834e-115">returned successfully.</span></span>|  
|<span data-ttu-id="b834e-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b834e-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b834e-117">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b834e-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b834e-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b834e-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b834e-119">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b834e-119">The call timed out.</span></span>|  
|<span data-ttu-id="b834e-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b834e-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b834e-121">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b834e-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b834e-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b834e-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b834e-123">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b834e-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b834e-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b834e-124">E_FAIL</span></span>|<span data-ttu-id="b834e-125">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b834e-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b834e-126">메서드가 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b834e-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b834e-127">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b834e-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b834e-128">설명</span><span class="sxs-lookup"><span data-stu-id="b834e-128">Remarks</span></span>  
 `ExecuteInAppDomain` <span data-ttu-id="b834e-129">호스트가 제어할 수 있도록 관리 되는 <xref:System.AppDomain> 에서 지정된 된 관리 되는 메서드를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b834e-129">allows the host to exercise control over which managed <xref:System.AppDomain> the specified managed method should be executed in.</span></span> <span data-ttu-id="b834e-130">값에 해당 하는 응용 프로그램 도메인 식별자의 값을 가져올 수는 <xref:System.AppDomain.Id%2A> 속성을 호출 하 여 [GetCurrentAppDomainId 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b834e-130">You can get the value of an application domain's identifier, which corresponds to the value of the <xref:System.AppDomain.Id%2A> property, by calling [GetCurrentAppDomainId Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b834e-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b834e-131">Requirements</span></span>  
 <span data-ttu-id="b834e-132">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b834e-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b834e-133">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b834e-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b834e-134">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="b834e-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="b834e-135">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="b834e-135">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b834e-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="b834e-136">See also</span></span>

- [<span data-ttu-id="b834e-137">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b834e-137">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
