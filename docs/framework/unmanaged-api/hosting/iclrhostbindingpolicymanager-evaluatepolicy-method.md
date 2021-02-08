---
description: '자세히 알아보기: ICLRHostBindingPolicyManager:: EvaluatePolicy 메서드'
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
ms.openlocfilehash: e92126a8c12d03ee21e4867754b1a418ef11d463
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789972"
---
# <a name="iclrhostbindingpolicymanagerevaluatepolicy-method"></a>ICLRHostBindingPolicyManager::EvaluatePolicy 메서드

호스트를 대신 하 여 바인딩 정책을 평가 합니다.  
  
## <a name="syntax"></a>구문  
  
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
  
## <a name="parameters"></a>매개 변수  

 `pwzReferenceIdentity`  
 진행 정책 평가 전에 어셈블리에 대 한 참조입니다.  
  
 `pbApplicationPolicy`  
 진행 정책 데이터를 포함 하는 버퍼에 대 한 포인터입니다.  
  
 `cbAppPolicySize`  
 진행 버퍼의 크기 `pbApplicationPolicy` 입니다.  
  
 `pwzPostPolicyReferenceIdentity`  
 제한이 새 정책 데이터를 평가한 후의 어셈블리에 대 한 참조입니다.  
  
 `pcchPostPolicyReferenceIdentity`  
 [in, out] 새 정책 데이터를 평가한 후의 어셈블리 id 참조 버퍼 크기에 대 한 포인터입니다.  
  
 `pdwPoliciesApplied`  
 제한이 적용 된 정책을 나타내는 [Ebindpolicylevels](ebindpolicylevels-enumeration.md) 값의 논리적 또는 조합에 대 한 포인터입니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|평가가 완료 되었습니다.|  
|E_INVALIDARG|`pwzReferenceIdentity`또는 `pbApplicationPolicy` 가 null 참조 인 경우|  
|ERROR_INSUFFICIENT_BUFFER|`cbAppPolicySize`가 너무 작습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
  
## <a name="remarks"></a>설명  

 메서드를 사용 하면 호스트 `EvaluatePolicy` 특정 어셈블리 버전 관리 요구 사항을 유지 하기 위해 호스트에서 바인딩 정책에 영향을 줄 수 있습니다. 정책 엔진 자체는 CLR 내에 유지 됩니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRHostBindingPolicyManager 인터페이스](iclrhostbindingpolicymanager-interface.md)
