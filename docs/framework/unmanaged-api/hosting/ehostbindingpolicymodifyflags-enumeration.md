---
title: EHostBindingPolicyModifyFlags 열거형
ms.date: 03/30/2017
api_name:
- EHostBindingPolicyModifyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EHostBindingPolicyModifyFlags
helpviewer_keywords:
- EHostBindingPolicyModifyFlags enumeration [.NET Framework hosting]
ms.assetid: 0339af16-ee1d-48ec-837d-a79d9a9c89f8
topic_type:
- apiref
ms.openlocfilehash: ec64f9bec0ee9b63796958b17c7f10b87692f1d0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686152"
---
# <a name="ehostbindingpolicymodifyflags-enumeration"></a>EHostBindingPolicyModifyFlags 열거형

호스트에서 소스 어셈블리의 정책 수정을 대상 어셈블리에 적용할 때 CLR (공용 언어 런타임)이 수행 해야 하는 리디렉션 형식을 지정할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum _hostBindingPolicyModifyFlags {  
    HOST_BINDING_POLICY_MODIFY_DEFAULT  = 0,  
    HOST_BINDING_POLICY_MODIFY_CHAIN    = 1,  
    HOST_BINDING_POLICY_MODIFY_REMOVE   = 2,  
    HOST_BINDING_POLICY_MODIFY_MAX      = 3  
} EHostBindingPolicyModifyFlags;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`HOST_BINDING_POLICY_MODIFY_CHAIN`|CLR이 소스 어셈블리의 정책 값을 대상 어셈블리의 정책 값에 연결 하도록 지정 합니다.|  
|`HOST_BINDING_POLICY_MODIFY_DEFAULT`|CLR에서 기본 작업을 수행 하도록 지정 합니다.|  
|`HOST_BINDING_POLICY_MODIFY_MAX`|CLR이 대상 어셈블리의 정책 값을 최대 값으로 설정 하도록 지정 합니다.|  
|`HOST_BINDING_POLICY_MODIFY_REMOVE`|CLR이 대상 어셈블리의 정책 값을 소스 어셈블리의 정책 값으로 바꾸도록 지정 합니다.|  
  
## <a name="remarks"></a>설명  

 [ICLRHostBindingPolicyManager:: ModifyApplicationPolicy](iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) 메서드는 형식의 매개 변수를 사용 합니다 `EHostBindingPolicyModifyFlags` .  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRHostBindingPolicyManager 인터페이스](iclrhostbindingpolicymanager-interface.md)
- [호스팅 열거형](hosting-enumerations.md)
