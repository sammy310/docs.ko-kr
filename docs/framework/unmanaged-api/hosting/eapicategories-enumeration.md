---
title: EApiCategories 열거형
ms.date: 03/30/2017
api_name:
- EApiCategories
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EApiCategories
helpviewer_keywords:
- EApiCategories enumeration [.NET Framework hosting]
ms.assetid: 3c4a8a5a-8a46-4ac9-947f-4959bc9d6ac6
topic_type:
- apiref
ms.openlocfilehash: d31b0190ef9a697fb27c849db080bec6c57618ae
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616387"
---
# <a name="eapicategories-enumeration"></a>EApiCategories 열거형
호스트에서 부분적으로 신뢰할 수 있는 코드에서 실행 되지 못하도록 차단할 수 있는 기능의 범주를 설명 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum {  
    eNoCategory               = 0,  
    eSynchronization          = 0x1,  
    eSharedState              = 0x2,  
    eExternalProcessMgmt      = 0x4,  
    eSelfAffectingProcessMgmt = 0x8,  
    eExternalThreading        = 0x10,  
    eSelfAffectingThreading   = 0x20,  
    eSecurityInfrastructure   = 0x40,  
    eUI                       = 0x80,  
    eMayLeakOnAbort           = 0x100,  
    eAll                      = 0x1ff  
} EHostProtectionCategories;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`eAll`|다른 필드가 적용 되는 모든 관리 되는 클래스와 멤버가 `EApiCategories` 부분적으로 신뢰할 수 있는 코드에서 실행 되지 못하도록 지정 합니다.|  
|`eExternalProcessMgmt`|외부 프로세스의 생성, 조작 및 소멸을 허용 하는 관리 되는 클래스와 멤버가 부분적으로 신뢰할 수 있는 코드에서 실행 되지 못하도록 지정 합니다.|  
|`eExternalThreading`|외부 스레드의 생성, 조작 및 소멸을 허용 하는 관리 되는 클래스와 멤버가 부분적으로 신뢰할 수 있는 코드에서 실행 되지 못하도록 지정 합니다.|  
|`eMayLeakOnAbort`|중단 시 메모리 누수가 발생할 수 있는 관리 되는 형식 및 멤버가 부분적으로 신뢰할 수 있는 코드에서 실행 되지 못하도록 지정 합니다.|  
|`eNoCategory`|관리 코드 범주가 부분적으로 신뢰할 수 있는 코드에서 실행 되는 것을 차단 하지 않도록 지정 합니다.|  
|`eSecurityInfrastructure`|부분적으로 신뢰할 수 있는 코드에서 CLR (공용 언어 런타임) 보안 인프라를 사용 하지 못하도록 차단 하도록 지정 합니다.|  
|`eSelfAffectingProcessMgmt`|기능이 호스팅된 프로세스에 영향을 줄 수 있는 관리 되는 클래스와 멤버가 부분적으로 신뢰할 수 있는 코드에서 실행 되지 못하도록 지정 합니다.|  
|`eSelfAffectingThreading`|기능이 호스팅된 프로세스의 스레드에 영향을 줄 수 있는 관리 되는 클래스와 멤버가 부분적으로 신뢰할 수 있는 코드에서 실행 되지 못하도록 지정 합니다.|  
|`eSharedState`|공유 상태를 노출 하는 관리 되는 클래스와 멤버가 부분적으로 신뢰할 수 있는 코드에서 실행 되지 못하도록 지정 합니다.|  
|`eSynchronization`|사용자 코드에서 잠금을 유지할 수 있도록 하는 공용 언어 런타임 클래스 및 멤버가 부분적으로 신뢰할 수 있는 코드에서 실행 되지 못하도록 지정 합니다.|  
|`eUI`|사용자 상호 작용을 허용 하거나 필요로 하는 관리 되는 클래스 및 멤버를 부분적으로 신뢰할 수 있는 코드에서 실행 하지 못하도록 지정 합니다.|  
  
## <a name="remarks"></a>설명  
 [ICLRHostProtectionManager:: SetProtectedCategories](iclrhostprotectionmanager-setprotectedcategories-method.md) 메서드는 형식의 매개 변수를 사용 합니다 `EApiCategories` .  
  
 `EApiCategories`열거형 및 메서드는 `SetProtectedCategories` 관리 되는 클래스와 직접적으로 관련이 <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> 있습니다. 관리 되는 클래스는 값에 직접 해당 하는 값을 가진 열거형과 함께 사용 되어 <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> `EApiCategories` 에서 설명 하는 범주에 해당 하는 기능을 노출 하는 관리 되는 형식 및 멤버를 표시 합니다 `EApiCategories` .  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRHostProtectionManager 인터페이스](iclrhostprotectionmanager-interface.md)
- [호스팅 열거형](hosting-enumerations.md)
