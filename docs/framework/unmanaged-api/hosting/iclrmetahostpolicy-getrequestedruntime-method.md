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
ms.openlocfilehash: 1b07029990ef529ded57bc569beff1061ad0f938
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140874"
---
# <a name="iclrmetahostpolicygetrequestedruntime-method"></a>ICLRMetaHostPolicy::GetRequestedRuntime 메서드

호스팅 정책, 관리되는 어셈블리, 버전 문자열 및 구성 스트림에 따라 CLR(공용 언어 런타임)의 기본 버전에 대한 인터페이스를 제공합니다. 이 메서드는 실제로 CLR을 로드 하거나 활성화 하지 않지만 정책 결과를 나타내는 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 인터페이스를 반환 합니다. 이 메서드는 [GetRequestedRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md), [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md), [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md), [CorBindToRuntimeByCfg](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)및 [getcorrequiredversion](../../../../docs/framework/unmanaged-api/hosting/getcorrequiredversion-function.md) 메서드를 대체 합니다.

## <a name="syntax"></a>구문

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

## <a name="parameters"></a>매개 변수

|name|설명|
|----------|-----------------|
|`dwPolicyFlags`|[in] 필수입니다. 바인딩 정책 및 원하는 수의 한정자를 나타내는 [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) 열거형의 멤버를 지정 합니다. 현재 사용할 수 있는 유일한 정책은 [METAHOST_POLICY_HIGHCOMPAT](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md)입니다.<br /><br /> 한정자에는 [METAHOST_POLICY_EMULATE_EXE_LAUNCH](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md), [METAHOST_POLICY_APPLY_UPGRADE_POLICY](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md), [METAHOST_POLICY_SHOW_ERROR_DIALOG](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md), [METAHOST_POLICY_USE_PROCESS_IMAGE_PATH](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md)및 METAHOST_POLICY_가 포함 됩니다. [ ENSURE_SKU_SUPPORTED](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md).|
|`pwzBinary`|[in] 선택적 항목으로, 어셈블리 파일 경로를 지정합니다.|
|`pCfgStream`|[in] 선택적 항목으로, 구성 파일을 <xref:System.Runtime.InteropServices.ComTypes.IStream?displayProperty=nameWithType>으로 지정합니다.|
|`pwzVersion`|[in, out] 선택 사항입니다. 로드할 기본 CLR 버전을 지정하거나 반환합니다.|
|`pcchVersion`|[in, out] 필수입니다. 버퍼 오버런을 방지하기 위해 `pwzVersion`의 예상 크기를 입력으로 지정합니다. `pwzVersion`이 null이면 사전 할당을 허용하기 위해 `GetRequestedRuntime`이 반환될 때 `pcchVersion`에 `pwzVersion`의 예상 크기가 포함됩니다. 그러지 않으면 `pcchVersion`에 `pwzVersion`에 기록된 문자 수가 포함됩니다.|
|`pwzImageVersion`|[out] 선택 사항입니다. `GetRequestedRuntime` 반환 될 때 반환 되는 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 인터페이스에 해당 하는 CLR 버전을 포함 합니다.|
|`pcchImageVersion`|[in, out] 선택 사항입니다. 버퍼 오버런을 방지하기 위해 `pwzImageVersion`의 크기를 입력으로 지정합니다. `pwzImageVersion`이 null이면 사전 할당을 허용하기 위해 `GetRequestedRuntime`이 반환될 때 `pcchImageVersion`에 `pwzImageVersion`의 필수 크기가 포함됩니다.|
|`pdwConfigFlags`|[out] 선택 사항입니다. `GetRequestedRuntime` 바인딩 프로세스 중에 구성 파일을 사용 하는 경우 [\<시작 >](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) 요소에 `useLegacyV2RuntimeActivationPolicy` 특성 집합이 있는지 여부를 나타내는 [METAHOST_CONFIG_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-config-flags-enumeration.md) 값과 값이 포함 `pdwConfigFlags`. 특성입니다. `pdwConfigFlags`에 [METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK](../../../../docs/framework/unmanaged-api/hosting/metahost-config-flags-enumeration.md) MASK를 적용 하 여 `useLegacyV2RuntimeActivationPolicy`와 관련 된 값을 가져옵니다.|
|`riid`|진행 요청 된 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 인터페이스에 대 한 인터페이스 식별자 IID_ICLRRuntimeInfo를 지정 합니다.|
|`ppRuntime`|제한이 `GetRequestedRuntime` 반환 될 때 해당 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 인터페이스에 대 한 포인터를 포함 합니다.|

## <a name="remarks"></a>주의

이 메서드가 성공하면 다음 요소 중 하나가 `<configuration><runtime>` 섹션 내의 구성 스트림에 있는 경우에만 반환된 런타임 인터페이스의 현재 기본 시작 플래그와 추가 플래그가 결합되는 부작용이 있습니다.

- `<gcServer enabled="true"/>`로 인해 `STARTUP_SERVER_GC`가 설정됩니다.

- `<etwEnable enabled="true"/>`로 인해 `STARTUP_ETW`가 설정됩니다.

- `<appDomainResourceMonitoring enabled="true"/>`로 인해 `STARTUP_ARM`가 설정됩니다.

결과 기본 `STARTUP_FLAGS` 값은 기본 시작 플래그를 사용하여 이전 목록에서 설정된 값의 비트 OR 조합입니다.

## <a name="return-value"></a>반환 값

이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.

|HRESULT|설명|
|-------------|-----------------|
|S_OK|메서드가 완료되었습니다.|
|E_POINTER|`pwzVersion`은 null이 아니고 `pcchVersion`은 null입니다.<br /><br /> 또는<br /><br /> `pwzImageVersion`은 null이 아니고 `pcchImageVersion`은 null입니다.|
|E_INVALIDARG|`dwPolicyFlags`가 `METAHOST_POLICY_HIGHCOMPAT`를 지정하지 않습니다.|
|ERROR_INSUFFICIENT_BUFFER|`pwzVersion`에 할당된 메모리가 부적합합니다.<br /><br /> 또는<br /><br /> `pwzImageVersion`에 할당된 메모리가 부적합합니다.|
|CLR_E_SHIM_RUNTIMELOAD|`dwPolicyFlags`에 METAHOST_POLICY_APPLY_UPGRADE_POLICY가 포함되어 있고, `pwzVersion` 및 `pcchVersion`이 둘 다 null입니다.|

## <a name="requirements"></a>요구 사항

**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.

**헤더:** MetaHost

**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.

**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]

## <a name="see-also"></a>참조

- [ICLRMetaHostPolicy 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md)
- [.NET Framework 4 및 4.5에 추가된 CLR 호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [호스팅](../../../../docs/framework/unmanaged-api/hosting/index.md)
