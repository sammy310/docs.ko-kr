---
title: ICLRMetaHostPolicy::GetRequestedRuntime 메서드
ms.date: 03/30/2017
api_name:
- ICLRMetaHostPolicy.GetRequestedRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHostPolicy::GetRequestedRuntime
helpviewer_keywords:
- GetRequestedRuntime method [.NET Framework hosting]
- ICLRMetaHostPolicy::GetRequestedRuntime method [.NET Framework hosting]
ms.assetid: 59ec1832-9cc1-4b5c-983d-03407e51de56
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 73d5c98500c510630b1f8d6081b654a6dbd88a5b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501697"
---
# <a name="iclrmetahostpolicygetrequestedruntime-method"></a><span data-ttu-id="64dc3-102">ICLRMetaHostPolicy::GetRequestedRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="64dc3-102">ICLRMetaHostPolicy::GetRequestedRuntime Method</span></span>

<span data-ttu-id="64dc3-103">호스팅 정책, 관리되는 어셈블리, 버전 문자열 및 구성 스트림에 따라 CLR(공용 언어 런타임)의 기본 버전에 대한 인터페이스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="64dc3-103">Provides an interface to a preferred version of the common language runtime (CLR) based on a hosting policy, managed assembly, version string, and configuration stream.</span></span> <span data-ttu-id="64dc3-104">이 메서드는 실제로 로드 하거나 반환 하지만 CLR을 활성화 합니다 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 정책 결과 나타내는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="64dc3-104">This method does not actually load or activate the CLR, but simply returns the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that represents the policy result.</span></span> <span data-ttu-id="64dc3-105">이 메서드를 대체 합니다 [GetRequestedRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)를 [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)합니다 [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md), [CorBindToRuntimeByCfg](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md), 및 [GetCORRequiredVersion](../../../../docs/framework/unmanaged-api/hosting/getcorrequiredversion-function.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="64dc3-105">This method supersedes the [GetRequestedRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md), [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md), [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md), [CorBindToRuntimeByCfg](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md), and [GetCORRequiredVersion](../../../../docs/framework/unmanaged-api/hosting/getcorrequiredversion-function.md) methods.</span></span>

## <a name="syntax"></a><span data-ttu-id="64dc3-106">구문</span><span class="sxs-lookup"><span data-stu-id="64dc3-106">Syntax</span></span>

```cpp
HRESULT GetRequestedRuntime(
    [in]  METAHOST_POLICY_FLAGS dwPolicyFlags,
    [in]  LPCWSTR pwzBinary,
    [in]  IStream *pCfgStream,
    [in, out, size_is(*pcchVersion)] LPWSTR pwzVersion,
    [in, out]  DWORD *pcchVersion,
    [out, size_is(*pcchImageVersion)] LPWSTR pwzImageVersion,
    [in, out]  DWORD *pcchImageVersion,
    [out] DWORD *pdwConfigFlags,
    [in]  REFIID  riid
    [out, iid_is(riid), retval] LPVOID *ppRuntime);
```

## <a name="parameters"></a><span data-ttu-id="64dc3-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="64dc3-107">Parameters</span></span>

|<span data-ttu-id="64dc3-108">이름</span><span class="sxs-lookup"><span data-stu-id="64dc3-108">Name</span></span>|<span data-ttu-id="64dc3-109">설명</span><span class="sxs-lookup"><span data-stu-id="64dc3-109">Description</span></span>|
|----------|-----------------|
|`dwPolicyFlags`|<span data-ttu-id="64dc3-110">[in] 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="64dc3-110">[in] Required.</span></span> <span data-ttu-id="64dc3-111">멤버를 지정 합니다 [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) 바인딩 정책 및 임의 개수의 한정자를 나타내는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="64dc3-111">Specifies a member of the [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) enumeration, representing a binding policy, and any number of modifiers.</span></span> <span data-ttu-id="64dc3-112">현재 사용할 수 있는 유일한 정책은 [METAHOST_POLICY_HIGHCOMPAT](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="64dc3-112">The only policy that is currently available is [METAHOST_POLICY_HIGHCOMPAT](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md).</span></span><br /><br /> <span data-ttu-id="64dc3-113">한정자를 포함 [METAHOST_POLICY_EMULATE_EXE_LAUNCH](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md)를 [METAHOST_POLICY_APPLY_UPGRADE_POLICY](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md)를 [METAHOST_POLICY_SHOW_ERROR_DIALOG](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md)합니다 [METAHOST_POLICY_USE_PROCESS_IMAGE_PATH](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md), 및 [METAHOST_POLICY_ENSURE_SKU_SUPPORTED](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="64dc3-113">Modifiers include [METAHOST_POLICY_EMULATE_EXE_LAUNCH](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md), [METAHOST_POLICY_APPLY_UPGRADE_POLICY](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md), [METAHOST_POLICY_SHOW_ERROR_DIALOG](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md), [METAHOST_POLICY_USE_PROCESS_IMAGE_PATH](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md), and [METAHOST_POLICY_ENSURE_SKU_SUPPORTED](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md).</span></span>|
|`pwzBinary`|<span data-ttu-id="64dc3-114">[in] 선택적 항목으로,</span><span class="sxs-lookup"><span data-stu-id="64dc3-114">[in] Optional.</span></span> <span data-ttu-id="64dc3-115">어셈블리 파일 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="64dc3-115">Specifies the assembly file path.</span></span>|
|`pCfgStream`|<span data-ttu-id="64dc3-116">[in] 선택적 항목으로,</span><span class="sxs-lookup"><span data-stu-id="64dc3-116">[in] Optional.</span></span> <span data-ttu-id="64dc3-117">구성 파일을 <xref:System.Runtime.InteropServices.ComTypes.IStream?displayProperty=nameWithType>으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="64dc3-117">Specifies the configuration file as a <xref:System.Runtime.InteropServices.ComTypes.IStream?displayProperty=nameWithType>.</span></span>|
|`pwzVersion`|<span data-ttu-id="64dc3-118">[in, out] 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="64dc3-118">[in, out] Optional.</span></span> <span data-ttu-id="64dc3-119">로드할 기본 CLR 버전을 지정하거나 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="64dc3-119">Specifies or returns the preferred CLR version to be loaded.</span></span>|
|`pcchVersion`|<span data-ttu-id="64dc3-120">[in, out] 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="64dc3-120">[in, out] Required.</span></span> <span data-ttu-id="64dc3-121">버퍼 오버런을 방지하기 위해 `pwzVersion`의 예상 크기를 입력으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="64dc3-121">Specifies the expected size of `pwzVersion` as input, to avoid buffer overruns.</span></span> <span data-ttu-id="64dc3-122">`pwzVersion`이 null이면 사전 할당을 허용하기 위해 `GetRequestedRuntime`이 반환될 때 `pcchVersion`에 `pwzVersion`의 예상 크기가 포함됩니다. 그러지 않으면 `pcchVersion`에 `pwzVersion`에 기록된 문자 수가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="64dc3-122">If `pwzVersion` is null, `pcchVersion` contains the expected size of `pwzVersion` when `GetRequestedRuntime` returns, to allow pre-allocation; otherwise, `pcchVersion` contains the number of characters written to `pwzVersion`.</span></span>|
|`pwzImageVersion`|<span data-ttu-id="64dc3-123">[out] 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="64dc3-123">[out] Optional.</span></span> <span data-ttu-id="64dc3-124">때 `GetRequestedRuntime` CLR 버전에 해당 하는 포함 된를 반환 합니다 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 반환 되는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="64dc3-124">When `GetRequestedRuntime` returns, contains the CLR version corresponding to the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that is returned.</span></span>|
|`pcchImageVersion`|<span data-ttu-id="64dc3-125">[in, out] 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="64dc3-125">[in, out] Optional.</span></span> <span data-ttu-id="64dc3-126">버퍼 오버런을 방지하기 위해 `pwzImageVersion`의 크기를 입력으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="64dc3-126">Specifies the size of `pwzImageVersion` as input to avoid buffer overruns.</span></span> <span data-ttu-id="64dc3-127">`pwzImageVersion`이 null이면 사전 할당을 허용하기 위해 `GetRequestedRuntime`이 반환될 때 `pcchImageVersion`에 `pwzImageVersion`의 필수 크기가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="64dc3-127">If `pwzImageVersion` is null, `pcchImageVersion` contains the required size of `pwzImageVersion` when `GetRequestedRuntime` returns, to allow pre-allocation.</span></span>|
|`pdwConfigFlags`|<span data-ttu-id="64dc3-128">[out] 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="64dc3-128">[out] Optional.</span></span> <span data-ttu-id="64dc3-129">경우 `GetRequestedRuntime` 를 반환 하는 경우 바인딩 과정에서 구성 파일을 사용 `pdwConfigFlags` 포함을 [METAHOST_CONFIG_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-config-flags-enumeration.md) 지정 하는 값 여부를 [ \<시작 >](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) 요소에는 `useLegacyV2RuntimeActivationPolicy` 특성 집합 및 특성의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="64dc3-129">If `GetRequestedRuntime` uses a configuration file during the binding process, when it returns, `pdwConfigFlags` contains a [METAHOST_CONFIG_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-config-flags-enumeration.md) value that indicates whether the [\<startup>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) element has the `useLegacyV2RuntimeActivationPolicy` attribute set, and the value of the attribute.</span></span> <span data-ttu-id="64dc3-130">적용 된 [METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK](../../../../docs/framework/unmanaged-api/hosting/metahost-config-flags-enumeration.md) 마스크를 `pdwConfigFlags` 관련 값을 가져오려면 `useLegacyV2RuntimeActivationPolicy`합니다.</span><span class="sxs-lookup"><span data-stu-id="64dc3-130">Apply the [METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK](../../../../docs/framework/unmanaged-api/hosting/metahost-config-flags-enumeration.md) mask to `pdwConfigFlags` to get the values relevant to `useLegacyV2RuntimeActivationPolicy`.</span></span>|
|`riid`|<span data-ttu-id="64dc3-131">[in] 요청 된 작업에 대 한 인터페이스 식별자 IID_ICLRRuntimeInfo를 지정 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="64dc3-131">[in] Specifies the interface identifier IID_ICLRRuntimeInfo for the requested [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>|
|`ppRuntime`|<span data-ttu-id="64dc3-132">[out] 때 `GetRequestedRuntime` 에 해당 요소에 대 한 포인터를 반환 하며 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="64dc3-132">[out] When `GetRequestedRuntime` returns, contains a pointer to the corresponding [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>|

## <a name="remarks"></a><span data-ttu-id="64dc3-133">설명</span><span class="sxs-lookup"><span data-stu-id="64dc3-133">Remarks</span></span>

<span data-ttu-id="64dc3-134">이 메서드가 성공하면 다음 요소 중 하나가 `<configuration><runtime>` 섹션 내의 구성 스트림에 있는 경우에만 반환된 런타임 인터페이스의 현재 기본 시작 플래그와 추가 플래그가 결합되는 부작용이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64dc3-134">When this method succeeds, it has the side effect of combining additional flags with the current default startup flags of the returned runtime interface, if and only if one or more of the following elements exist in the configuration stream within the `<configuration><runtime>` section:</span></span>

- <span data-ttu-id="64dc3-135">`<gcServer enabled="true"/>`로 인해 `STARTUP_SERVER_GC`가 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="64dc3-135">`<gcServer enabled="true"/>` causes `STARTUP_SERVER_GC` to be set.</span></span>

- <span data-ttu-id="64dc3-136">`<etwEnable enabled="true"/>`로 인해 `STARTUP_ETW`가 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="64dc3-136">`<etwEnable enabled="true"/>` causes `STARTUP_ETW` to be set.</span></span>

- <span data-ttu-id="64dc3-137">`<appDomainResourceMonitoring enabled="true"/>`로 인해 `STARTUP_ARM`가 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="64dc3-137">`<appDomainResourceMonitoring enabled="true"/>` causes `STARTUP_ARM` to be set.</span></span>

<span data-ttu-id="64dc3-138">결과 기본 `STARTUP_FLAGS` 값은 기본 시작 플래그를 사용하여 이전 목록에서 설정된 값의 비트 OR 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="64dc3-138">The resulting default `STARTUP_FLAGS` value is the bitwise OR combination of the values that are set from the preceding list with the default startup flags.</span></span>

## <a name="return-value"></a><span data-ttu-id="64dc3-139">반환 값</span><span class="sxs-lookup"><span data-stu-id="64dc3-139">Return Value</span></span>

<span data-ttu-id="64dc3-140">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="64dc3-140">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>

|<span data-ttu-id="64dc3-141">HRESULT</span><span class="sxs-lookup"><span data-stu-id="64dc3-141">HRESULT</span></span>|<span data-ttu-id="64dc3-142">설명</span><span class="sxs-lookup"><span data-stu-id="64dc3-142">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="64dc3-143">S_OK</span><span class="sxs-lookup"><span data-stu-id="64dc3-143">S_OK</span></span>|<span data-ttu-id="64dc3-144">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="64dc3-144">The method completed successfully.</span></span>|
|<span data-ttu-id="64dc3-145">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="64dc3-145">E_POINTER</span></span>|<span data-ttu-id="64dc3-146">`pwzVersion`은 null이 아니고 `pcchVersion`은 null입니다.</span><span class="sxs-lookup"><span data-stu-id="64dc3-146">`pwzVersion` is not null and `pcchVersion` is null.</span></span><br /><br /> <span data-ttu-id="64dc3-147">또는</span><span class="sxs-lookup"><span data-stu-id="64dc3-147">-or-</span></span><br /><br /> <span data-ttu-id="64dc3-148">`pwzImageVersion`은 null이 아니고 `pcchImageVersion`은 null입니다.</span><span class="sxs-lookup"><span data-stu-id="64dc3-148">`pwzImageVersion` is not null and `pcchImageVersion` is null.</span></span>|
|<span data-ttu-id="64dc3-149">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="64dc3-149">E_INVALIDARG</span></span>|<span data-ttu-id="64dc3-150">`dwPolicyFlags`가 `METAHOST_POLICY_HIGHCOMPAT`를 지정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="64dc3-150">`dwPolicyFlags` does not specify `METAHOST_POLICY_HIGHCOMPAT`.</span></span>|
|<span data-ttu-id="64dc3-151">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="64dc3-151">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="64dc3-152">`pwzVersion`에 할당된 메모리가 부적합합니다.</span><span class="sxs-lookup"><span data-stu-id="64dc3-152">The memory allocated to `pwzVersion` is inadequate.</span></span><br /><br /> <span data-ttu-id="64dc3-153">또는</span><span class="sxs-lookup"><span data-stu-id="64dc3-153">-or-</span></span><br /><br /> <span data-ttu-id="64dc3-154">`pwzImageVersion`에 할당된 메모리가 부적합합니다.</span><span class="sxs-lookup"><span data-stu-id="64dc3-154">The memory allocated to `pwzImageVersion` is inadequate.</span></span>|
|<span data-ttu-id="64dc3-155">CLR_E_SHIM_RUNTIMELOAD</span><span class="sxs-lookup"><span data-stu-id="64dc3-155">CLR_E_SHIM_RUNTIMELOAD</span></span>|<span data-ttu-id="64dc3-156">`dwPolicyFlags`에 METAHOST_POLICY_APPLY_UPGRADE_POLICY가 포함되어 있고, `pwzVersion` 및 `pcchVersion`이 둘 다 null입니다.</span><span class="sxs-lookup"><span data-stu-id="64dc3-156">`dwPolicyFlags` includes METAHOST_POLICY_APPLY_UPGRADE_POLICY, and both `pwzVersion` and `pcchVersion` are null.</span></span>|

## <a name="requirements"></a><span data-ttu-id="64dc3-157">요구 사항</span><span class="sxs-lookup"><span data-stu-id="64dc3-157">Requirements</span></span>

<span data-ttu-id="64dc3-158">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="64dc3-158">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="64dc3-159">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="64dc3-159">**Header:** MetaHost.h</span></span>

<span data-ttu-id="64dc3-160">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="64dc3-160">**Library:** Included as a resource in MSCorEE.dll</span></span>

<span data-ttu-id="64dc3-161">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64dc3-161">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="64dc3-162">참고자료</span><span class="sxs-lookup"><span data-stu-id="64dc3-162">See also</span></span>

- [<span data-ttu-id="64dc3-163">ICLRMetaHostPolicy 인터페이스</span><span class="sxs-lookup"><span data-stu-id="64dc3-163">ICLRMetaHostPolicy Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md)
- [<span data-ttu-id="64dc3-164">.NET Framework 4 및 4.5에 추가된 CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="64dc3-164">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="64dc3-165">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="64dc3-165">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="64dc3-166">호스팅</span><span class="sxs-lookup"><span data-stu-id="64dc3-166">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
