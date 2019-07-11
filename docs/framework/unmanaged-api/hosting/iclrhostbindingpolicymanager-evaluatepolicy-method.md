---
title: ICLRHostBindingPolicyManager::EvaluatePolicy 메서드
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager.EvaluatePolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager::EvaluatePolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::EvaluatePolicy method [.NET Framework hosting]
- EvaluatePolicy method [.NET Framework hosting]
ms.assetid: 3a3a9446-7a4e-4836-9b27-5c536c15993d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7d23b2371e7cc3c9d1e91af061c19b4fb0dbc69e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779688"
---
# <a name="iclrhostbindingpolicymanagerevaluatepolicy-method"></a><span data-ttu-id="bac4a-102">ICLRHostBindingPolicyManager::EvaluatePolicy 메서드</span><span class="sxs-lookup"><span data-stu-id="bac4a-102">ICLRHostBindingPolicyManager::EvaluatePolicy Method</span></span>
<span data-ttu-id="bac4a-103">호스트를 대신 하 여 바인딩 정책을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="bac4a-103">Evaluates binding policy on behalf of the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bac4a-104">구문</span><span class="sxs-lookup"><span data-stu-id="bac4a-104">Syntax</span></span>  
  
```cpp  
HRESULT EvaluatePolicy (  
    [in] LPCWSTR     pwzReferenceIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [out, size_is(*pcchPostPolicyReferenceIdentity)] LPWSTR pwzPostPolicyReferenceIdentity,  
    [in, out] DWORD *pcchPostPolicyReferenceIdentity,  
    [out] DWORD     *pdwPoliciesApplied  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bac4a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bac4a-105">Parameters</span></span>  
 `pwzReferenceIdentity`  
 <span data-ttu-id="bac4a-106">[in] 정책 평가 하기 전에 어셈블리에 대 한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="bac4a-106">[in] A reference to the assembly before the policy evaluation.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="bac4a-107">[in] 정책 데이터를 포함 하는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bac4a-107">[in] A pointer to a buffer that contains the policy data.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="bac4a-108">[in] 크기는 `pbApplicationPolicy` 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="bac4a-108">[in] The size of the `pbApplicationPolicy` buffer.</span></span>  
  
 `pwzPostPolicyReferenceIdentity`  
 <span data-ttu-id="bac4a-109">[out] 새 정책 데이터를 평가한 후 어셈블리 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="bac4a-109">[out] A reference to the assembly after the evaluation of the new policy data.</span></span>  
  
 `pcchPostPolicyReferenceIdentity`  
 <span data-ttu-id="bac4a-110">[out에서] 새 정책 데이터를 평가한 후 어셈블리 identity 참조 버퍼의 크기에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bac4a-110">[in, out] A pointer to the size of the assembly identity reference buffer after the evaluation of the new policy data.</span></span>  
  
 `pdwPoliciesApplied`  
 <span data-ttu-id="bac4a-111">[out] 논리 OR 조합에 대 한 포인터 [EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md) 어떤 정책이 적용 되었는지 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bac4a-111">[out] A pointer to a logical OR combination of [EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md) values, indicating which policies have been applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bac4a-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="bac4a-112">Return Value</span></span>  
  
|<span data-ttu-id="bac4a-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bac4a-113">HRESULT</span></span>|<span data-ttu-id="bac4a-114">Description</span><span class="sxs-lookup"><span data-stu-id="bac4a-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bac4a-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="bac4a-115">S_OK</span></span>|<span data-ttu-id="bac4a-116">평가 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="bac4a-116">The evaluation completed successfully.</span></span>|  
|<span data-ttu-id="bac4a-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="bac4a-117">E_INVALIDARG</span></span>|<span data-ttu-id="bac4a-118">중 하나 `pwzReferenceIdentity` 또는 `pbApplicationPolicy` 가 null 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="bac4a-118">Either `pwzReferenceIdentity` or `pbApplicationPolicy` is a null reference.</span></span>|  
|<span data-ttu-id="bac4a-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="bac4a-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="bac4a-120">`cbAppPolicySize` 너무 작습니다.</span><span class="sxs-lookup"><span data-stu-id="bac4a-120">`cbAppPolicySize` is too small.</span></span>|  
|<span data-ttu-id="bac4a-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bac4a-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bac4a-122">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bac4a-122">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bac4a-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bac4a-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bac4a-124">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bac4a-124">The call timed out.</span></span>|  
|<span data-ttu-id="bac4a-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bac4a-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bac4a-126">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bac4a-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bac4a-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bac4a-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bac4a-128">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bac4a-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bac4a-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bac4a-129">E_FAIL</span></span>|<span data-ttu-id="bac4a-130">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bac4a-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bac4a-131">E_FAIL을 반환 하는 메서드를 CLR 더 이상 프로세스 내에서 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="bac4a-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bac4a-132">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bac4a-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bac4a-133">설명</span><span class="sxs-lookup"><span data-stu-id="bac4a-133">Remarks</span></span>  
 <span data-ttu-id="bac4a-134">`EvaluatePolicy` 메서드를 사용 하면 호스트 관련 어셈블리를 유지 하기 위해 바인딩 정책을 호스트 버전 관리 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bac4a-134">The `EvaluatePolicy` method allows the host to influence binding policy to maintain host-specific assembly versioning requirements.</span></span> <span data-ttu-id="bac4a-135">정책 엔진 자체 CLR 내에서 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bac4a-135">The policy engine itself remains inside the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bac4a-136">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bac4a-136">Requirements</span></span>  
 <span data-ttu-id="bac4a-137">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bac4a-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bac4a-138">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bac4a-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bac4a-139">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="bac4a-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bac4a-140">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bac4a-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bac4a-141">참고자료</span><span class="sxs-lookup"><span data-stu-id="bac4a-141">See also</span></span>

- [<span data-ttu-id="bac4a-142">ICLRHostBindingPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bac4a-142">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
