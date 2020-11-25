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
ms.openlocfilehash: 9840217abdf8b3e1d0917b7447572b6860c181c8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720310"
---
# <a name="iclrhostbindingpolicymanagerevaluatepolicy-method"></a><span data-ttu-id="bdd21-102">ICLRHostBindingPolicyManager::EvaluatePolicy 메서드</span><span class="sxs-lookup"><span data-stu-id="bdd21-102">ICLRHostBindingPolicyManager::EvaluatePolicy Method</span></span>

<span data-ttu-id="bdd21-103">호스트를 대신 하 여 바인딩 정책을 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdd21-103">Evaluates binding policy on behalf of the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdd21-104">구문</span><span class="sxs-lookup"><span data-stu-id="bdd21-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="bdd21-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bdd21-105">Parameters</span></span>  

 `pwzReferenceIdentity`  
 <span data-ttu-id="bdd21-106">진행 정책 평가 전에 어셈블리에 대 한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="bdd21-106">[in] A reference to the assembly before the policy evaluation.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="bdd21-107">진행 정책 데이터를 포함 하는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bdd21-107">[in] A pointer to a buffer that contains the policy data.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="bdd21-108">진행 버퍼의 크기 `pbApplicationPolicy` 입니다.</span><span class="sxs-lookup"><span data-stu-id="bdd21-108">[in] The size of the `pbApplicationPolicy` buffer.</span></span>  
  
 `pwzPostPolicyReferenceIdentity`  
 <span data-ttu-id="bdd21-109">제한이 새 정책 데이터를 평가한 후의 어셈블리에 대 한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="bdd21-109">[out] A reference to the assembly after the evaluation of the new policy data.</span></span>  
  
 `pcchPostPolicyReferenceIdentity`  
 <span data-ttu-id="bdd21-110">[in, out] 새 정책 데이터를 평가한 후의 어셈블리 id 참조 버퍼 크기에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bdd21-110">[in, out] A pointer to the size of the assembly identity reference buffer after the evaluation of the new policy data.</span></span>  
  
 `pdwPoliciesApplied`  
 <span data-ttu-id="bdd21-111">제한이 적용 된 정책을 나타내는 [Ebindpolicylevels](ebindpolicylevels-enumeration.md) 값의 논리적 또는 조합에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bdd21-111">[out] A pointer to a logical OR combination of [EBindPolicyLevels](ebindpolicylevels-enumeration.md) values, indicating which policies have been applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bdd21-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="bdd21-112">Return Value</span></span>  
  
|<span data-ttu-id="bdd21-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bdd21-113">HRESULT</span></span>|<span data-ttu-id="bdd21-114">설명</span><span class="sxs-lookup"><span data-stu-id="bdd21-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bdd21-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="bdd21-115">S_OK</span></span>|<span data-ttu-id="bdd21-116">평가가 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd21-116">The evaluation completed successfully.</span></span>|  
|<span data-ttu-id="bdd21-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="bdd21-117">E_INVALIDARG</span></span>|<span data-ttu-id="bdd21-118">`pwzReferenceIdentity`또는 `pbApplicationPolicy` 가 null 참조 인 경우</span><span class="sxs-lookup"><span data-stu-id="bdd21-118">Either `pwzReferenceIdentity` or `pbApplicationPolicy` is a null reference.</span></span>|  
|<span data-ttu-id="bdd21-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="bdd21-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="bdd21-120">`cbAppPolicySize`가 너무 작습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd21-120">`cbAppPolicySize` is too small.</span></span>|  
|<span data-ttu-id="bdd21-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bdd21-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bdd21-122">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd21-122">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bdd21-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bdd21-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bdd21-124">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd21-124">The call timed out.</span></span>|  
|<span data-ttu-id="bdd21-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bdd21-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bdd21-126">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd21-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bdd21-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bdd21-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bdd21-128">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd21-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bdd21-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bdd21-129">E_FAIL</span></span>|<span data-ttu-id="bdd21-130">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd21-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bdd21-131">메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd21-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bdd21-132">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdd21-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bdd21-133">설명</span><span class="sxs-lookup"><span data-stu-id="bdd21-133">Remarks</span></span>  

 <span data-ttu-id="bdd21-134">메서드를 사용 하면 호스트 `EvaluatePolicy` 특정 어셈블리 버전 관리 요구 사항을 유지 하기 위해 호스트에서 바인딩 정책에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd21-134">The `EvaluatePolicy` method allows the host to influence binding policy to maintain host-specific assembly versioning requirements.</span></span> <span data-ttu-id="bdd21-135">정책 엔진 자체는 CLR 내에 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdd21-135">The policy engine itself remains inside the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdd21-136">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bdd21-136">Requirements</span></span>  

 <span data-ttu-id="bdd21-137">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bdd21-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdd21-138">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="bdd21-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bdd21-139">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdd21-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bdd21-140">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bdd21-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdd21-141">참조</span><span class="sxs-lookup"><span data-stu-id="bdd21-141">See also</span></span>

- [<span data-ttu-id="bdd21-142">ICLRHostBindingPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bdd21-142">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)
