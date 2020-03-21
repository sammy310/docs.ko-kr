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
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a>ICLRHostBindingPolicyManager::ModifyApplicationPolicy 메서드
지정된 어셈블리에 대한 바인딩 정책을 수정하고 정책의 새 버전을 만듭니다.  
  
## <a name="syntax"></a>구문  
  
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
  
## <a name="parameters"></a>매개 변수  
 `pwzSourceAssemblyIdentity`  
 【인】 수정할 어셈블리의 ID입니다.  
  
 `pwzTargetAssemblyIdentity`  
 【인】 수정된 어셈블리의 새 ID입니다.  
  
 `pbApplicationPolicy`  
 【인】 어셈블리를 수정할 바인딩 정책 데이터가 포함된 버퍼에 대한 포인터입니다.  
  
 `cbAppPolicySize`  
 【인】 대체할 바인딩 정책의 크기입니다.  
  
 `dwPolicyModifyFlags`  
 【인】 [EHostBindingPolicy의](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) 논리적 OR 조합수정플래그 값으로 리디렉션 제어를 나타냅니다.  
  
 `pbNewApplicationPolicy`  
 【아웃】 새 바인딩 정책 데이터를 포함하는 버퍼에 대한 포인터입니다.  
  
 `pcbNewAppPolicySize`  
 【인, 아웃】 새 바인딩 정책 버퍼의 크기에 대한 포인터입니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|정책이 성공적으로 수정되었습니다.|  
|E_INVALIDARG|`pwzSourceAssemblyIdentity`또는 `pwzTargetAssemblyIdentity` null 참조였습니다.|  
|ERROR_INSUFFICIENT_BUFFER|`pbNewApplicationPolicy`가 너무 작습니다.|  
|HOST_E_CLRNOTAVAILABLE|공통 언어 런타임(CLR)이 프로세스에 로드되지 않았거나 CLR이 관리 코드를 실행하거나 호출을 성공적으로 처리할 수 없는 상태입니다.|  
|HOST_E_TIMEOUT|통화 시간이 시간 미정으로 확인되었습니다.|  
|HOST_E_NOT_OWNER|호출자는 잠금을 소유하지 않습니다.|  
|HOST_E_ABANDONED|차단된 스레드 또는 파이버가 대기하는 동안 이벤트가 취소되었습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생했습니다. 메서드가 E_FAIL 반환하면 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다. 호스팅 메서드에 대한 후속 호출은 HOST_E_CLRNOTAVAILABLE 반환합니다.|  
  
## <a name="remarks"></a>설명  
 메서드를 `ModifyApplicationPolicy` 두 번 호출할 수 있습니다. 첫 번째 호출은 `pbNewApplicationPolicy` 매개 변수에 대한 null 값을 제공해야 합니다. 이 호출은 `pcbNewAppPolicySize`에 필요한 값으로 반환됩니다. 두 번째 호출은 에 `pcbNewAppPolicySize`대해 이 값을 제공하고 에 `pbNewApplicationPolicy`대한 해당 크기의 버퍼를 가리해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MSCorE.h  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRHostBindingPolicyManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
