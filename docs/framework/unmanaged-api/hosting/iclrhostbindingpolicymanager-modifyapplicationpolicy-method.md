---
description: '자세히 알아보기: ICLRHostBindingPolicyManager:: ModifyApplicationPolicy 메서드'
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
ms.openlocfilehash: 3f7d992f4b7d24233da175814f991106bb97a937
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789933"
---
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a><span data-ttu-id="f89bf-103">ICLRHostBindingPolicyManager::ModifyApplicationPolicy 메서드</span><span class="sxs-lookup"><span data-stu-id="f89bf-103">ICLRHostBindingPolicyManager::ModifyApplicationPolicy Method</span></span>

<span data-ttu-id="f89bf-104">지정 된 어셈블리에 대 한 바인딩 정책을 수정 하 고 정책의 새 버전을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f89bf-104">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f89bf-105">구문</span><span class="sxs-lookup"><span data-stu-id="f89bf-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="f89bf-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f89bf-106">Parameters</span></span>  

 `pwzSourceAssemblyIdentity`  
 <span data-ttu-id="f89bf-107">진행 수정할 어셈블리의 id입니다.</span><span class="sxs-lookup"><span data-stu-id="f89bf-107">[in] The identity of the assembly to modify.</span></span>  
  
 `pwzTargetAssemblyIdentity`  
 <span data-ttu-id="f89bf-108">진행 수정 된 어셈블리의 새 id입니다.</span><span class="sxs-lookup"><span data-stu-id="f89bf-108">[in] The new identity of the modified assembly.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="f89bf-109">진행 수정할 어셈블리에 대 한 바인딩 정책 데이터를 포함 하는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f89bf-109">[in] A pointer to a buffer that contains the binding policy data for the assembly to modify.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="f89bf-110">진행 대체할 바인딩 정책의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="f89bf-110">[in] The size of the binding policy to be replaced.</span></span>  
  
 `dwPolicyModifyFlags`  
 <span data-ttu-id="f89bf-111">진행 리디렉션 제어를 나타내는 [EHostBindingPolicyModifyFlags](ehostbindingpolicymodifyflags-enumeration.md) 값의 논리적 또는 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="f89bf-111">[in] A logical OR combination of [EHostBindingPolicyModifyFlags](ehostbindingpolicymodifyflags-enumeration.md) values, indicating control of redirection.</span></span>  
  
 `pbNewApplicationPolicy`  
 <span data-ttu-id="f89bf-112">제한이 새 바인딩 정책 데이터를 포함 하는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f89bf-112">[out] A pointer to a buffer that contains the new binding policy data.</span></span>  
  
 `pcbNewAppPolicySize`  
 <span data-ttu-id="f89bf-113">[in, out] 새 바인딩 정책 버퍼의 크기에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f89bf-113">[in, out] A pointer to the size of the new binding policy buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f89bf-114">Return Value</span><span class="sxs-lookup"><span data-stu-id="f89bf-114">Return Value</span></span>  
  
|<span data-ttu-id="f89bf-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f89bf-115">HRESULT</span></span>|<span data-ttu-id="f89bf-116">설명</span><span class="sxs-lookup"><span data-stu-id="f89bf-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f89bf-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="f89bf-117">S_OK</span></span>|<span data-ttu-id="f89bf-118">정책을 수정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f89bf-118">The policy was modified successfully.</span></span>|  
|<span data-ttu-id="f89bf-119">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f89bf-119">E_INVALIDARG</span></span>|<span data-ttu-id="f89bf-120">`pwzSourceAssemblyIdentity` 또는 `pwzTargetAssemblyIdentity` 가 null 참조 인 경우</span><span class="sxs-lookup"><span data-stu-id="f89bf-120">`pwzSourceAssemblyIdentity` or `pwzTargetAssemblyIdentity` was a null reference.</span></span>|  
|<span data-ttu-id="f89bf-121">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="f89bf-121">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="f89bf-122">`pbNewApplicationPolicy`가 너무 작습니다.</span><span class="sxs-lookup"><span data-stu-id="f89bf-122">`pbNewApplicationPolicy` is too small.</span></span>|  
|<span data-ttu-id="f89bf-123">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f89bf-123">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f89bf-124">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f89bf-124">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f89bf-125">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f89bf-125">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f89bf-126">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f89bf-126">The call timed out.</span></span>|  
|<span data-ttu-id="f89bf-127">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f89bf-127">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f89bf-128">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f89bf-128">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f89bf-129">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f89bf-129">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f89bf-130">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f89bf-130">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f89bf-131">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f89bf-131">E_FAIL</span></span>|<span data-ttu-id="f89bf-132">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f89bf-132">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f89bf-133">메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f89bf-133">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f89bf-134">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f89bf-134">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f89bf-135">설명</span><span class="sxs-lookup"><span data-stu-id="f89bf-135">Remarks</span></span>  

 <span data-ttu-id="f89bf-136">`ModifyApplicationPolicy`메서드를 두 번 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f89bf-136">The `ModifyApplicationPolicy` method can be called twice.</span></span> <span data-ttu-id="f89bf-137">첫 번째 호출은 매개 변수에 null 값을 제공 해야 합니다 `pbNewApplicationPolicy` .</span><span class="sxs-lookup"><span data-stu-id="f89bf-137">The first call should supply a null value for the `pbNewApplicationPolicy` parameter.</span></span> <span data-ttu-id="f89bf-138">이 호출은에 대해 필요한 값과 함께를 반환 합니다 `pcbNewAppPolicySize` .</span><span class="sxs-lookup"><span data-stu-id="f89bf-138">This call will return with the necessary value for `pcbNewAppPolicySize`.</span></span> <span data-ttu-id="f89bf-139">두 번째 호출에서는에 대해이 값 `pcbNewAppPolicySize` 을 제공 하 고에 대 한 해당 크기의 버퍼를 가리킵니다 `pbNewApplicationPolicy` .</span><span class="sxs-lookup"><span data-stu-id="f89bf-139">The second call should supply this value for `pcbNewAppPolicySize`, and point to a buffer of that size for `pbNewApplicationPolicy`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f89bf-140">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f89bf-140">Requirements</span></span>  

 <span data-ttu-id="f89bf-141">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f89bf-141">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f89bf-142">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f89bf-142">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f89bf-143">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f89bf-143">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f89bf-144">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f89bf-144">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f89bf-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f89bf-145">See also</span></span>

- [<span data-ttu-id="f89bf-146">ICLRHostBindingPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f89bf-146">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)
