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
ms.openlocfilehash: 9600573a0a730cee10247d5644d587e75856cdd9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141182"
---
# <a name="iclrhostbindingpolicymanagerevaluatepolicy-method"></a><span data-ttu-id="5db43-102">ICLRHostBindingPolicyManager::EvaluatePolicy 메서드</span><span class="sxs-lookup"><span data-stu-id="5db43-102">ICLRHostBindingPolicyManager::EvaluatePolicy Method</span></span>
<span data-ttu-id="5db43-103">호스트를 대신 하 여 바인딩 정책을 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-103">Evaluates binding policy on behalf of the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5db43-104">구문</span><span class="sxs-lookup"><span data-stu-id="5db43-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="5db43-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5db43-105">Parameters</span></span>  
 `pwzReferenceIdentity`  
 <span data-ttu-id="5db43-106">진행 정책 평가 전에 어셈블리에 대 한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-106">[in] A reference to the assembly before the policy evaluation.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="5db43-107">진행 정책 데이터를 포함 하는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-107">[in] A pointer to a buffer that contains the policy data.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="5db43-108">진행 `pbApplicationPolicy` 버퍼의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-108">[in] The size of the `pbApplicationPolicy` buffer.</span></span>  
  
 `pwzPostPolicyReferenceIdentity`  
 <span data-ttu-id="5db43-109">제한이 새 정책 데이터를 평가한 후의 어셈블리에 대 한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-109">[out] A reference to the assembly after the evaluation of the new policy data.</span></span>  
  
 `pcchPostPolicyReferenceIdentity`  
 <span data-ttu-id="5db43-110">[in, out] 새 정책 데이터를 평가한 후의 어셈블리 id 참조 버퍼 크기에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-110">[in, out] A pointer to the size of the assembly identity reference buffer after the evaluation of the new policy data.</span></span>  
  
 `pdwPoliciesApplied`  
 <span data-ttu-id="5db43-111">제한이 적용 된 정책을 나타내는 [Ebindpolicylevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md) 값의 논리적 또는 조합에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-111">[out] A pointer to a logical OR combination of [EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md) values, indicating which policies have been applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5db43-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="5db43-112">Return Value</span></span>  
  
|<span data-ttu-id="5db43-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5db43-113">HRESULT</span></span>|<span data-ttu-id="5db43-114">설명</span><span class="sxs-lookup"><span data-stu-id="5db43-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5db43-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="5db43-115">S_OK</span></span>|<span data-ttu-id="5db43-116">평가가 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-116">The evaluation completed successfully.</span></span>|  
|<span data-ttu-id="5db43-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="5db43-117">E_INVALIDARG</span></span>|<span data-ttu-id="5db43-118">`pwzReferenceIdentity` 또는 `pbApplicationPolicy`은 (는) null 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-118">Either `pwzReferenceIdentity` or `pbApplicationPolicy` is a null reference.</span></span>|  
|<span data-ttu-id="5db43-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="5db43-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="5db43-120">`cbAppPolicySize` 너무 작습니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-120">`cbAppPolicySize` is too small.</span></span>|  
|<span data-ttu-id="5db43-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5db43-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5db43-122">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-122">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5db43-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5db43-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5db43-124">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-124">The call timed out.</span></span>|  
|<span data-ttu-id="5db43-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5db43-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5db43-126">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5db43-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5db43-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5db43-128">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5db43-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5db43-129">E_FAIL</span></span>|<span data-ttu-id="5db43-130">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5db43-131">메서드가 E_FAIL을 반환한 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5db43-132">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5db43-133">주의</span><span class="sxs-lookup"><span data-stu-id="5db43-133">Remarks</span></span>  
 <span data-ttu-id="5db43-134">`EvaluatePolicy` 메서드를 사용 하면 호스트 특정 어셈블리 버전 관리 요구 사항을 유지 하기 위해 호스트에서 바인딩 정책에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-134">The `EvaluatePolicy` method allows the host to influence binding policy to maintain host-specific assembly versioning requirements.</span></span> <span data-ttu-id="5db43-135">정책 엔진 자체는 CLR 내에 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-135">The policy engine itself remains inside the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5db43-136">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5db43-136">Requirements</span></span>  
 <span data-ttu-id="5db43-137">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5db43-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5db43-138">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="5db43-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5db43-139">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5db43-140">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5db43-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5db43-141">참조</span><span class="sxs-lookup"><span data-stu-id="5db43-141">See also</span></span>

- [<span data-ttu-id="5db43-142">ICLRHostBindingPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5db43-142">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
