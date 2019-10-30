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
ms.openlocfilehash: c847f177f48d72f28192d1efabe93c65a7b3f4b8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120500"
---
# <a name="iclrruntimehostexecuteinappdomain-method"></a><span data-ttu-id="9747b-102">ICLRRuntimeHost::ExecuteInAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="9747b-102">ICLRRuntimeHost::ExecuteInAppDomain Method</span></span>
<span data-ttu-id="9747b-103">지정 된 관리 코드를 실행할 <xref:System.AppDomain>를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9747b-103">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9747b-104">구문</span><span class="sxs-lookup"><span data-stu-id="9747b-104">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteInAppDomain(  
    [in] DWORD AppDomainId,   
    [in] FExecuteInDomainCallback pCallback,   
    [in] void* cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9747b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9747b-105">Parameters</span></span>  
 `AppDomainId`  
 <span data-ttu-id="9747b-106">진행 지정 된 메서드를 실행할 <xref:System.AppDomain>의 숫자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9747b-106">[in] The numeric ID of the <xref:System.AppDomain> in which to execute the specified method.</span></span>  
  
 `pCallback`  
 <span data-ttu-id="9747b-107">진행 지정 된 <xref:System.AppDomain>내에서 실행할 함수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9747b-107">[in] A pointer to the function to execute within the specified <xref:System.AppDomain>.</span></span>  
  
 `cookie`  
 <span data-ttu-id="9747b-108">진행 호출자가 할당 한 불투명 메모리에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9747b-108">[in] A pointer to opaque caller-allocated memory.</span></span> <span data-ttu-id="9747b-109">이 매개 변수는 CLR (공용 언어 런타임)에서 도메인 콜백에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9747b-109">This parameter is passed by the common language runtime (CLR) to the domain callback.</span></span> <span data-ttu-id="9747b-110">런타임 관리 힙 메모리가 아닙니다. 이 메모리의 할당 및 수명은 모두 호출자에 의해 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9747b-110">It is not runtime-managed heap memory; both the allocation and lifetime of this memory are controlled by the caller.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9747b-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="9747b-111">Return Value</span></span>  
  
|<span data-ttu-id="9747b-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9747b-112">HRESULT</span></span>|<span data-ttu-id="9747b-113">설명</span><span class="sxs-lookup"><span data-stu-id="9747b-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9747b-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="9747b-114">S_OK</span></span>|<span data-ttu-id="9747b-115">`ExecuteInAppDomain` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9747b-115">`ExecuteInAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="9747b-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9747b-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9747b-117">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9747b-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9747b-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9747b-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9747b-119">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9747b-119">The call timed out.</span></span>|  
|<span data-ttu-id="9747b-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9747b-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9747b-121">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9747b-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9747b-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9747b-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9747b-123">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9747b-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9747b-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9747b-124">E_FAIL</span></span>|<span data-ttu-id="9747b-125">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9747b-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9747b-126">메서드가 E_FAIL을 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9747b-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9747b-127">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9747b-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9747b-128">주의</span><span class="sxs-lookup"><span data-stu-id="9747b-128">Remarks</span></span>  
 <span data-ttu-id="9747b-129">`ExecuteInAppDomain`를 사용 하면 호스트에서 지정 된 관리 되는 메서드를 실행 해야 하는 관리 되는 <xref:System.AppDomain>를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9747b-129">`ExecuteInAppDomain` allows the host to exercise control over which managed <xref:System.AppDomain> the specified managed method should be executed in.</span></span> <span data-ttu-id="9747b-130">[GetCurrentAppDomainId 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)를 호출 하 여 <xref:System.AppDomain.Id%2A> 속성의 값에 해당 하는 응용 프로그램 도메인 식별자의 값을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9747b-130">You can get the value of an application domain's identifier, which corresponds to the value of the <xref:System.AppDomain.Id%2A> property, by calling [GetCurrentAppDomainId Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9747b-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9747b-131">Requirements</span></span>  
 <span data-ttu-id="9747b-132">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9747b-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9747b-133">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9747b-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9747b-134">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9747b-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9747b-135">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9747b-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9747b-136">참조</span><span class="sxs-lookup"><span data-stu-id="9747b-136">See also</span></span>

- [<span data-ttu-id="9747b-137">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9747b-137">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
