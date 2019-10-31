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
ms.openlocfilehash: d5323538447e083a0c727e43261dd68337182b9b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141083"
---
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a>ICLRHostBindingPolicyManager::ModifyApplicationPolicy 메서드
지정 된 어셈블리에 대 한 바인딩 정책을 수정 하 고 정책의 새 버전을 만듭니다.  
  
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
 진행 수정할 어셈블리의 id입니다.  
  
 `pwzTargetAssemblyIdentity`  
 진행 수정 된 어셈블리의 새 id입니다.  
  
 `pbApplicationPolicy`  
 진행 수정할 어셈블리에 대 한 바인딩 정책 데이터를 포함 하는 버퍼에 대 한 포인터입니다.  
  
 `cbAppPolicySize`  
 진행 대체할 바인딩 정책의 크기입니다.  
  
 `dwPolicyModifyFlags`  
 진행 리디렉션 제어를 나타내는 [EHostBindingPolicyModifyFlags](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) 값의 논리적 또는 조합입니다.  
  
 `pbNewApplicationPolicy`  
 제한이 새 바인딩 정책 데이터를 포함 하는 버퍼에 대 한 포인터입니다.  
  
 `pcbNewAppPolicySize`  
 [in, out] 새 바인딩 정책 버퍼의 크기에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|정책을 수정 했습니다.|  
|E_INVALIDARG|`pwzSourceAssemblyIdentity` 또는 `pwzTargetAssemblyIdentity`은 (는) null 참조입니다.|  
|ERROR_INSUFFICIENT_BUFFER|`pbNewApplicationPolicy` 너무 작습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL을 반환한 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다. 호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.|  
  
## <a name="remarks"></a>주의  
 `ModifyApplicationPolicy` 메서드를 두 번 호출할 수 있습니다. 첫 번째 호출은 `pbNewApplicationPolicy` 매개 변수에 대해 null 값을 제공 해야 합니다. 이 호출은 `pcbNewAppPolicySize`에 필요한 값과 함께를 반환 합니다. 두 번째 호출은 `pcbNewAppPolicySize`에 대해이 값을 제공 하 고 `pbNewApplicationPolicy`에 해당 하는 크기의 버퍼를 가리킵니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRHostBindingPolicyManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
