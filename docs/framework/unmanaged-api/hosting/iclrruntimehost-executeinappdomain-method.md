---
description: '자세히 알아보기: ICLRRuntimeHost:: ExecuteInAppDomain 메서드'
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
ms.openlocfilehash: 6640713b55e05817f39af819d5e41ee1f2a10b68
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799748"
---
# <a name="iclrruntimehostexecuteinappdomain-method"></a><span data-ttu-id="0f283-103">ICLRRuntimeHost::ExecuteInAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="0f283-103">ICLRRuntimeHost::ExecuteInAppDomain Method</span></span>

<span data-ttu-id="0f283-104">지정 된 <xref:System.AppDomain> 관리 코드를 실행할를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f283-104">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f283-105">구문</span><span class="sxs-lookup"><span data-stu-id="0f283-105">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteInAppDomain(  
    [in] DWORD AppDomainId,
    [in] FExecuteInDomainCallback pCallback,
    [in] void* cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f283-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0f283-106">Parameters</span></span>  

 `AppDomainId`  
 <span data-ttu-id="0f283-107">진행 지정 된 메서드를 실행할의 숫자 ID입니다 <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="0f283-107">[in] The numeric ID of the <xref:System.AppDomain> in which to execute the specified method.</span></span>  
  
 `pCallback`  
 <span data-ttu-id="0f283-108">진행 지정 된 내에서 실행할 함수에 대 한 포인터입니다 <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="0f283-108">[in] A pointer to the function to execute within the specified <xref:System.AppDomain>.</span></span>  
  
 `cookie`  
 <span data-ttu-id="0f283-109">진행 호출자가 할당 한 불투명 메모리에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0f283-109">[in] A pointer to opaque caller-allocated memory.</span></span> <span data-ttu-id="0f283-110">이 매개 변수는 CLR (공용 언어 런타임)에서 도메인 콜백에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f283-110">This parameter is passed by the common language runtime (CLR) to the domain callback.</span></span> <span data-ttu-id="0f283-111">런타임 관리 힙 메모리가 아닙니다. 이 메모리의 할당 및 수명은 모두 호출자에 의해 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f283-111">It is not runtime-managed heap memory; both the allocation and lifetime of this memory are controlled by the caller.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0f283-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="0f283-112">Return Value</span></span>  
  
|<span data-ttu-id="0f283-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0f283-113">HRESULT</span></span>|<span data-ttu-id="0f283-114">설명</span><span class="sxs-lookup"><span data-stu-id="0f283-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0f283-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="0f283-115">S_OK</span></span>|<span data-ttu-id="0f283-116">`ExecuteInAppDomain` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0f283-116">`ExecuteInAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="0f283-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0f283-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0f283-118">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f283-118">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0f283-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0f283-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0f283-120">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0f283-120">The call timed out.</span></span>|  
|<span data-ttu-id="0f283-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0f283-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0f283-122">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f283-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0f283-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0f283-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0f283-124">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0f283-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0f283-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0f283-125">E_FAIL</span></span>|<span data-ttu-id="0f283-126">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0f283-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0f283-127">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f283-127">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0f283-128">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f283-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f283-129">설명</span><span class="sxs-lookup"><span data-stu-id="0f283-129">Remarks</span></span>  

 <span data-ttu-id="0f283-130">`ExecuteInAppDomain` 호스트에서 <xref:System.AppDomain> 지정 된 관리 되는 메서드를 실행 해야 하는 관리를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f283-130">`ExecuteInAppDomain` allows the host to exercise control over which managed <xref:System.AppDomain> the specified managed method should be executed in.</span></span> <span data-ttu-id="0f283-131"><xref:System.AppDomain.Id%2A> [GetCurrentAppDomainId 메서드](iclrruntimehost-getcurrentappdomainid-method.md)를 호출 하 여 속성의 값에 해당 하는 응용 프로그램 도메인 식별자의 값을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f283-131">You can get the value of an application domain's identifier, which corresponds to the value of the <xref:System.AppDomain.Id%2A> property, by calling [GetCurrentAppDomainId Method](iclrruntimehost-getcurrentappdomainid-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f283-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0f283-132">Requirements</span></span>  

 <span data-ttu-id="0f283-133">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f283-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f283-134">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="0f283-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0f283-135">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f283-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0f283-136">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f283-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f283-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0f283-137">See also</span></span>

- [<span data-ttu-id="0f283-138">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0f283-138">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
