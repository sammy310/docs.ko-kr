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
ms.openlocfilehash: d8df78e3d5cebe5378dfba11dc0ea93cc8e346eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178097"
---
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a><span data-ttu-id="ba919-102">ICLRHostBindingPolicyManager::ModifyApplicationPolicy 메서드</span><span class="sxs-lookup"><span data-stu-id="ba919-102">ICLRHostBindingPolicyManager::ModifyApplicationPolicy Method</span></span>
<span data-ttu-id="ba919-103">지정된 어셈블리에 대한 바인딩 정책을 수정하고 정책의 새 버전을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ba919-103">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba919-104">구문</span><span class="sxs-lookup"><span data-stu-id="ba919-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="ba919-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ba919-105">Parameters</span></span>  
 `pwzSourceAssemblyIdentity`  
 <span data-ttu-id="ba919-106">【인】 수정할 어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ba919-106">[in] The identity of the assembly to modify.</span></span>  
  
 `pwzTargetAssemblyIdentity`  
 <span data-ttu-id="ba919-107">【인】 수정된 어셈블리의 새 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ba919-107">[in] The new identity of the modified assembly.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="ba919-108">【인】 어셈블리를 수정할 바인딩 정책 데이터가 포함된 버퍼에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ba919-108">[in] A pointer to a buffer that contains the binding policy data for the assembly to modify.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="ba919-109">【인】 대체할 바인딩 정책의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="ba919-109">[in] The size of the binding policy to be replaced.</span></span>  
  
 `dwPolicyModifyFlags`  
 <span data-ttu-id="ba919-110">【인】 [EHostBindingPolicy의](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) 논리적 OR 조합수정플래그 값으로 리디렉션 제어를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ba919-110">[in] A logical OR combination of [EHostBindingPolicyModifyFlags](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) values, indicating control of redirection.</span></span>  
  
 `pbNewApplicationPolicy`  
 <span data-ttu-id="ba919-111">【아웃】 새 바인딩 정책 데이터를 포함하는 버퍼에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ba919-111">[out] A pointer to a buffer that contains the new binding policy data.</span></span>  
  
 `pcbNewAppPolicySize`  
 <span data-ttu-id="ba919-112">【인, 아웃】 새 바인딩 정책 버퍼의 크기에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ba919-112">[in, out] A pointer to the size of the new binding policy buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ba919-113">Return Value</span><span class="sxs-lookup"><span data-stu-id="ba919-113">Return Value</span></span>  
  
|<span data-ttu-id="ba919-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ba919-114">HRESULT</span></span>|<span data-ttu-id="ba919-115">Description</span><span class="sxs-lookup"><span data-stu-id="ba919-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ba919-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="ba919-116">S_OK</span></span>|<span data-ttu-id="ba919-117">정책이 성공적으로 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ba919-117">The policy was modified successfully.</span></span>|  
|<span data-ttu-id="ba919-118">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ba919-118">E_INVALIDARG</span></span>|<span data-ttu-id="ba919-119">`pwzSourceAssemblyIdentity`또는 `pwzTargetAssemblyIdentity` null 참조였습니다.</span><span class="sxs-lookup"><span data-stu-id="ba919-119">`pwzSourceAssemblyIdentity` or `pwzTargetAssemblyIdentity` was a null reference.</span></span>|  
|<span data-ttu-id="ba919-120">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="ba919-120">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="ba919-121">`pbNewApplicationPolicy`가 너무 작습니다.</span><span class="sxs-lookup"><span data-stu-id="ba919-121">`pbNewApplicationPolicy` is too small.</span></span>|  
|<span data-ttu-id="ba919-122">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ba919-122">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ba919-123">공통 언어 런타임(CLR)이 프로세스에 로드되지 않았거나 CLR이 관리 코드를 실행하거나 호출을 성공적으로 처리할 수 없는 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="ba919-123">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ba919-124">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ba919-124">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ba919-125">통화 시간이 시간 미정으로 확인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ba919-125">The call timed out.</span></span>|  
|<span data-ttu-id="ba919-126">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ba919-126">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ba919-127">호출자는 잠금을 소유하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ba919-127">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ba919-128">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ba919-128">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ba919-129">차단된 스레드 또는 파이버가 대기하는 동안 이벤트가 취소되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ba919-129">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ba919-130">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ba919-130">E_FAIL</span></span>|<span data-ttu-id="ba919-131">알 수 없는 치명적인 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="ba919-131">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ba919-132">메서드가 E_FAIL 반환하면 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba919-132">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ba919-133">호스팅 메서드에 대한 후속 호출은 HOST_E_CLRNOTAVAILABLE 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ba919-133">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba919-134">설명</span><span class="sxs-lookup"><span data-stu-id="ba919-134">Remarks</span></span>  
 <span data-ttu-id="ba919-135">메서드를 `ModifyApplicationPolicy` 두 번 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba919-135">The `ModifyApplicationPolicy` method can be called twice.</span></span> <span data-ttu-id="ba919-136">첫 번째 호출은 `pbNewApplicationPolicy` 매개 변수에 대한 null 값을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba919-136">The first call should supply a null value for the `pbNewApplicationPolicy` parameter.</span></span> <span data-ttu-id="ba919-137">이 호출은 `pcbNewAppPolicySize`에 필요한 값으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba919-137">This call will return with the necessary value for `pcbNewAppPolicySize`.</span></span> <span data-ttu-id="ba919-138">두 번째 호출은 에 `pcbNewAppPolicySize`대해 이 값을 제공하고 에 `pbNewApplicationPolicy`대한 해당 크기의 버퍼를 가리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba919-138">The second call should supply this value for `pcbNewAppPolicySize`, and point to a buffer of that size for `pbNewApplicationPolicy`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba919-139">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ba919-139">Requirements</span></span>  
 <span data-ttu-id="ba919-140">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba919-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba919-141">**헤더:** MSCorE.h</span><span class="sxs-lookup"><span data-stu-id="ba919-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ba919-142">**라이브러리:** MSCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="ba919-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ba919-143">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba919-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba919-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ba919-144">See also</span></span>

- [<span data-ttu-id="ba919-145">ICLRHostBindingPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ba919-145">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
