---
title: ICLRHostBindingPolicyManager::ModifyApplicationPolicy 메서드
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager.ModifyApplicationPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager::ModifyApplicationPolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::ModifyApplicationPolicy method [.NET Framework hosting]
- ModifyApplicationPolicy method [.NET Framework hosting]
ms.assetid: d82d633e-cce6-427c-8b02-8227e34e12ba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 07a4998f86958e21fffc8ba8657ec9f2a170f43e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59112439"
---
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a><span data-ttu-id="28339-102">ICLRHostBindingPolicyManager::ModifyApplicationPolicy 메서드</span><span class="sxs-lookup"><span data-stu-id="28339-102">ICLRHostBindingPolicyManager::ModifyApplicationPolicy Method</span></span>
<span data-ttu-id="28339-103">지정된 된 어셈블리에 대 한 바인딩 정책 수정 하 고 정책의 새 버전을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="28339-103">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28339-104">구문</span><span class="sxs-lookup"><span data-stu-id="28339-104">Syntax</span></span>  
  
```  
HRESULT  ModifyApplicationPolicy (  
    [in] LPCWSTR     pwzSourceAssemblyIdentity,   
    [in] LPCWSTR     pwzTargetAssemblyIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [in] DWORD       dwPolicyModifyFlags,  
    [out, size_is(*pcbNewAppPolicySize)] BYTE *pbNewApplicationPolicy,   
    [in, out] DWORD *pcbNewAppPolicySize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28339-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="28339-105">Parameters</span></span>  
 `pwzSourceAssemblyIdentity`  
 <span data-ttu-id="28339-106">[in] 수정할 어셈블리의 id입니다.</span><span class="sxs-lookup"><span data-stu-id="28339-106">[in] The identity of the assembly to modify.</span></span>  
  
 `pwzTargetAssemblyIdentity`  
 <span data-ttu-id="28339-107">[in] 수정 된 어셈블리의 새 id입니다.</span><span class="sxs-lookup"><span data-stu-id="28339-107">[in] The new identity of the modified assembly.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="28339-108">[in] 수정 하려면 어셈블리에 대 한 바인딩 정책 데이터를 포함 하는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="28339-108">[in] A pointer to a buffer that contains the binding policy data for the assembly to modify.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="28339-109">[in] 크기 교체 바인딩 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="28339-109">[in] The size of the binding policy to be replaced.</span></span>  
  
 `dwPolicyModifyFlags`  
 <span data-ttu-id="28339-110">[in] 논리 OR 조합을 [EHostBindingPolicyModifyFlags](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) 의도치 않은 리디렉션의 컨트롤을 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="28339-110">[in] A logical OR combination of [EHostBindingPolicyModifyFlags](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) values, indicating control of redirection.</span></span>  
  
 `pbNewApplicationPolicy`  
 <span data-ttu-id="28339-111">[out] 새 바인딩 정책 데이터를 포함 하는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="28339-111">[out] A pointer to a buffer that contains the new binding policy data.</span></span>  
  
 `pcbNewAppPolicySize`  
 <span data-ttu-id="28339-112">[out에서] 새 바인딩 정책 버퍼의 크기에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="28339-112">[in, out] A pointer to the size of the new binding policy buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="28339-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="28339-113">Return Value</span></span>  
  
|<span data-ttu-id="28339-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="28339-114">HRESULT</span></span>|<span data-ttu-id="28339-115">설명</span><span class="sxs-lookup"><span data-stu-id="28339-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="28339-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="28339-116">S_OK</span></span>|<span data-ttu-id="28339-117">정책을 수정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="28339-117">The policy was modified successfully.</span></span>|  
|<span data-ttu-id="28339-118">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="28339-118">E_INVALIDARG</span></span>|<span data-ttu-id="28339-119">`pwzSourceAssemblyIdentity` 또는 `pwzTargetAssemblyIdentity` null 참조 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="28339-119">`pwzSourceAssemblyIdentity` or `pwzTargetAssemblyIdentity` was a null reference.</span></span>|  
|<span data-ttu-id="28339-120">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="28339-120">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="28339-121">`pbNewApplicationPolicy` 너무 작습니다.</span><span class="sxs-lookup"><span data-stu-id="28339-121">`pbNewApplicationPolicy` is too small.</span></span>|  
|<span data-ttu-id="28339-122">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="28339-122">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="28339-123">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="28339-123">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="28339-124">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="28339-124">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="28339-125">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="28339-125">The call timed out.</span></span>|  
|<span data-ttu-id="28339-126">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="28339-126">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="28339-127">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="28339-127">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="28339-128">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="28339-128">HOST_E_ABANDONED</span></span>|<span data-ttu-id="28339-129">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28339-129">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="28339-130">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="28339-130">E_FAIL</span></span>|<span data-ttu-id="28339-131">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="28339-131">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="28339-132">E_FAIL을 반환 하는 메서드를 CLR 더 이상 프로세스 내에서 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="28339-132">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="28339-133">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="28339-133">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28339-134">설명</span><span class="sxs-lookup"><span data-stu-id="28339-134">Remarks</span></span>  
 <span data-ttu-id="28339-135">`ModifyApplicationPolicy` 메서드를 두 번 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28339-135">The `ModifyApplicationPolicy` method can be called twice.</span></span> <span data-ttu-id="28339-136">첫 번째 호출에 null 값을 제공 해야 합니다 `pbNewApplicationPolicy` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="28339-136">The first call should supply a null value for the `pbNewApplicationPolicy` parameter.</span></span> <span data-ttu-id="28339-137">이 호출은 필요한 값으로 반환 `pcbNewAppPolicySize`합니다.</span><span class="sxs-lookup"><span data-stu-id="28339-137">This call will return with the necessary value for `pcbNewAppPolicySize`.</span></span> <span data-ttu-id="28339-138">두 번째 호출에 대 한이 값을 제공 해야 `pcbNewAppPolicySize`에 대 한 크기의 버퍼를 가리킵니다 `pbNewApplicationPolicy`합니다.</span><span class="sxs-lookup"><span data-stu-id="28339-138">The second call should supply this value for `pcbNewAppPolicySize`, and point to a buffer of that size for `pbNewApplicationPolicy`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28339-139">요구 사항</span><span class="sxs-lookup"><span data-stu-id="28339-139">Requirements</span></span>  
 <span data-ttu-id="28339-140">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="28339-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28339-141">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="28339-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="28339-142">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="28339-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="28339-143">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28339-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28339-144">참고자료</span><span class="sxs-lookup"><span data-stu-id="28339-144">See also</span></span>

- [<span data-ttu-id="28339-145">ICLRHostBindingPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="28339-145">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
