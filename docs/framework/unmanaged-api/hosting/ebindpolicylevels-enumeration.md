---
title: EBindPolicyLevels 열거형
ms.date: 03/30/2017
api_name:
- EBindPolicyLevels
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EBindPolicyLevels
helpviewer_keywords:
- EBindPolicyLevels enumeration [.NET Framework hosting]
ms.assetid: a9e00b4f-b6d0-4257-bd88-4fe9af97b8fa
topic_type:
- apiref
ms.openlocfilehash: 81aef6beb9ee6d622519738d24fdd0a4d42a75b1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136560"
---
# <a name="ebindpolicylevels-enumeration"></a>EBindPolicyLevels 열거형
어셈블리 정책을 적용 하거나 수정할 수준을 지정 하는 플래그를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum {  
    ePolicyLevelNone         = 0x0,  
    ePolicyLevelRetargetable = 0x1,  
    ePolicyUnifiedToCLR      = 0x2,  
    ePolicyLevelApp          = 0x4,  
    ePolicyLevelPublisher    = 0x8,  
    ePolicyLevelHost         = 0x10,  
    ePolicyLevelAdmin        = 0x20  
    ePolicyPortability       = 0x40  
} EBindPolicyLevels;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`ePolicyLevelAdmin`|정책을 관리자 수준에서 적용 하도록 지정 합니다.|  
|`ePolicyLevelApp`|응용 프로그램 수준에서 정책을 적용 하도록 지정 합니다.|  
|`ePolicyLevelHost`|정책을 호스트 수준에서 적용 하도록 지정 합니다.|  
|`ePolicyLevelNone`|정책 수준 플래그를 지정 하지 않습니다.|  
|`ePolicyLevelPublisher`|정책을 게시자 수준에서 적용 하도록 지정 합니다.|  
|`ePolicyLevelRetargetable`|정책을 변수 수준에서 적용할 수 있도록 지정 합니다.|  
|`ePolicyPortability`|정책이 .NET Framework 어셈블리 구현 간의 이식성을 지원 하도록 지정 합니다. [\<supportportability> >](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md) 구성 파일 요소를 참조 하세요.|  
|`ePolicyUnifiedToCLR`|정책을 CLR (공용 언어 런타임)과 통합 하도록 지정 합니다.|  
  
## <a name="remarks"></a>주의  
 이 열거형은 응용 프로그램 정책에서 변경 내용을 지정 하기 위해 [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) 인터페이스의 메서드에 전달 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRAssemblyIdentityManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [호스팅 열거형](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
