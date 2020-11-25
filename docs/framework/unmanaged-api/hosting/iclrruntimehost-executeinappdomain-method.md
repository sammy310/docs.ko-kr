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
ms.openlocfilehash: 4c28c4a5cc64b20c9ac9c57e1aef5e7b90a20e01
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728890"
---
# <a name="iclrruntimehostexecuteinappdomain-method"></a><span data-ttu-id="adc45-102">ICLRRuntimeHost::ExecuteInAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="adc45-102">ICLRRuntimeHost::ExecuteInAppDomain Method</span></span>

<span data-ttu-id="adc45-103">지정 된 <xref:System.AppDomain> 관리 코드를 실행할를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="adc45-103">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adc45-104">구문</span><span class="sxs-lookup"><span data-stu-id="adc45-104">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteInAppDomain(  
    [in] DWORD AppDomainId,
    [in] FExecuteInDomainCallback pCallback,
    [in] void* cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="adc45-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="adc45-105">Parameters</span></span>  

 `AppDomainId`  
 <span data-ttu-id="adc45-106">진행 지정 된 메서드를 실행할의 숫자 ID입니다 <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="adc45-106">[in] The numeric ID of the <xref:System.AppDomain> in which to execute the specified method.</span></span>  
  
 `pCallback`  
 <span data-ttu-id="adc45-107">진행 지정 된 내에서 실행할 함수에 대 한 포인터입니다 <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="adc45-107">[in] A pointer to the function to execute within the specified <xref:System.AppDomain>.</span></span>  
  
 `cookie`  
 <span data-ttu-id="adc45-108">진행 호출자가 할당 한 불투명 메모리에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="adc45-108">[in] A pointer to opaque caller-allocated memory.</span></span> <span data-ttu-id="adc45-109">이 매개 변수는 CLR (공용 언어 런타임)에서 도메인 콜백에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="adc45-109">This parameter is passed by the common language runtime (CLR) to the domain callback.</span></span> <span data-ttu-id="adc45-110">런타임 관리 힙 메모리가 아닙니다. 이 메모리의 할당 및 수명은 모두 호출자에 의해 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="adc45-110">It is not runtime-managed heap memory; both the allocation and lifetime of this memory are controlled by the caller.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="adc45-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="adc45-111">Return Value</span></span>  
  
|<span data-ttu-id="adc45-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="adc45-112">HRESULT</span></span>|<span data-ttu-id="adc45-113">설명</span><span class="sxs-lookup"><span data-stu-id="adc45-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="adc45-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="adc45-114">S_OK</span></span>|<span data-ttu-id="adc45-115">`ExecuteInAppDomain` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="adc45-115">`ExecuteInAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="adc45-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="adc45-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="adc45-117">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adc45-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="adc45-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="adc45-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="adc45-119">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="adc45-119">The call timed out.</span></span>|  
|<span data-ttu-id="adc45-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="adc45-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="adc45-121">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="adc45-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="adc45-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="adc45-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="adc45-123">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="adc45-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="adc45-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="adc45-124">E_FAIL</span></span>|<span data-ttu-id="adc45-125">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="adc45-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="adc45-126">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="adc45-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="adc45-127">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="adc45-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="adc45-128">설명</span><span class="sxs-lookup"><span data-stu-id="adc45-128">Remarks</span></span>  

 <span data-ttu-id="adc45-129">`ExecuteInAppDomain` 호스트에서 <xref:System.AppDomain> 지정 된 관리 되는 메서드를 실행 해야 하는 관리를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adc45-129">`ExecuteInAppDomain` allows the host to exercise control over which managed <xref:System.AppDomain> the specified managed method should be executed in.</span></span> <span data-ttu-id="adc45-130"><xref:System.AppDomain.Id%2A> [GetCurrentAppDomainId 메서드](iclrruntimehost-getcurrentappdomainid-method.md)를 호출 하 여 속성의 값에 해당 하는 응용 프로그램 도메인 식별자의 값을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adc45-130">You can get the value of an application domain's identifier, which corresponds to the value of the <xref:System.AppDomain.Id%2A> property, by calling [GetCurrentAppDomainId Method](iclrruntimehost-getcurrentappdomainid-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="adc45-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="adc45-131">Requirements</span></span>  

 <span data-ttu-id="adc45-132">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="adc45-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="adc45-133">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="adc45-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="adc45-134">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="adc45-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="adc45-135">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="adc45-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adc45-136">참조</span><span class="sxs-lookup"><span data-stu-id="adc45-136">See also</span></span>

- [<span data-ttu-id="adc45-137">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="adc45-137">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
