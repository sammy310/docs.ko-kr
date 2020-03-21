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
ms.openlocfilehash: c012e4e2b5e41737f7bbe6a0fb887693b0ba22c8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176424"
---
# <a name="iclrruntimehostexecuteinappdomain-method"></a><span data-ttu-id="0aa19-102">ICLRRuntimeHost::ExecuteInAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="0aa19-102">ICLRRuntimeHost::ExecuteInAppDomain Method</span></span>
<span data-ttu-id="0aa19-103"><xref:System.AppDomain> 지정된 관리 코드를 실행할 수 있는 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0aa19-103">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0aa19-104">구문</span><span class="sxs-lookup"><span data-stu-id="0aa19-104">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteInAppDomain(  
    [in] DWORD AppDomainId,
    [in] FExecuteInDomainCallback pCallback,
    [in] void* cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0aa19-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0aa19-105">Parameters</span></span>  
 `AppDomainId`  
 <span data-ttu-id="0aa19-106">【인】 지정된 메서드를 <xref:System.AppDomain> 실행할 수 있는 숫자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0aa19-106">[in] The numeric ID of the <xref:System.AppDomain> in which to execute the specified method.</span></span>  
  
 `pCallback`  
 <span data-ttu-id="0aa19-107">【인】 지정된 <xref:System.AppDomain>내에서 실행할 함수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0aa19-107">[in] A pointer to the function to execute within the specified <xref:System.AppDomain>.</span></span>  
  
 `cookie`  
 <span data-ttu-id="0aa19-108">【인】 불투명 호출자 할당 메모리에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0aa19-108">[in] A pointer to opaque caller-allocated memory.</span></span> <span data-ttu-id="0aa19-109">이 매개 변수는 공통 언어 런타임(CLR)을 통해 도메인 콜백으로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="0aa19-109">This parameter is passed by the common language runtime (CLR) to the domain callback.</span></span> <span data-ttu-id="0aa19-110">런타임 관리 힙 메모리가 아닙니다. 이 메모리의 할당과 수명은 모두 호출자에 의해 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="0aa19-110">It is not runtime-managed heap memory; both the allocation and lifetime of this memory are controlled by the caller.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0aa19-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="0aa19-111">Return Value</span></span>  
  
|<span data-ttu-id="0aa19-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0aa19-112">HRESULT</span></span>|<span data-ttu-id="0aa19-113">Description</span><span class="sxs-lookup"><span data-stu-id="0aa19-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0aa19-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="0aa19-114">S_OK</span></span>|<span data-ttu-id="0aa19-115">`ExecuteInAppDomain`성공적으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="0aa19-115">`ExecuteInAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="0aa19-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0aa19-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0aa19-117">CLR이 프로세스에 로드되지 않았거나 CLR이 관리 코드를 실행하거나 호출을 성공적으로 처리할 수 없는 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="0aa19-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0aa19-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0aa19-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0aa19-119">통화 시간이 시간 미정으로 확인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0aa19-119">The call timed out.</span></span>|  
|<span data-ttu-id="0aa19-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0aa19-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0aa19-121">호출자는 잠금을 소유하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0aa19-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0aa19-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0aa19-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0aa19-123">차단된 스레드 또는 파이버가 대기하는 동안 이벤트가 취소되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0aa19-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0aa19-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0aa19-124">E_FAIL</span></span>|<span data-ttu-id="0aa19-125">알 수 없는 치명적인 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="0aa19-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0aa19-126">메서드가 E_FAIL 반환하면 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0aa19-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0aa19-127">호스팅 메서드에 대한 후속 호출은 HOST_E_CLRNOTAVAILABLE 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0aa19-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0aa19-128">설명</span><span class="sxs-lookup"><span data-stu-id="0aa19-128">Remarks</span></span>  
 <span data-ttu-id="0aa19-129">`ExecuteInAppDomain`을 사용하면 호스트가 지정된 <xref:System.AppDomain> 관리 방법을 실행해야 하는 관리되는 제어 권한을 행사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0aa19-129">`ExecuteInAppDomain` allows the host to exercise control over which managed <xref:System.AppDomain> the specified managed method should be executed in.</span></span> <span data-ttu-id="0aa19-130"><xref:System.AppDomain.Id%2A> [GetCurrentAppDomainId 메서드를](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)호출하여 속성 값에 해당하는 응용 프로그램 도메인의 식별자 값을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0aa19-130">You can get the value of an application domain's identifier, which corresponds to the value of the <xref:System.AppDomain.Id%2A> property, by calling [GetCurrentAppDomainId Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0aa19-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0aa19-131">Requirements</span></span>  
 <span data-ttu-id="0aa19-132">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0aa19-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0aa19-133">**헤더:** MSCorE.h</span><span class="sxs-lookup"><span data-stu-id="0aa19-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0aa19-134">**라이브러리:** MSCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="0aa19-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0aa19-135">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0aa19-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0aa19-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0aa19-136">See also</span></span>

- [<span data-ttu-id="0aa19-137">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0aa19-137">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
