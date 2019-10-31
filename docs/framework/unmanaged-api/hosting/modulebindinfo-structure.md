---
title: ModuleBindInfo 구조체
ms.date: 03/30/2017
api_name:
- ModuleBindInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ModuleBindInfo
helpviewer_keywords:
- ModuleBindInfo structure [.NET Framework hosting]
ms.assetid: 632d4adc-dbc9-4ce8-9397-abc3285c1c69
topic_type:
- apiref
ms.openlocfilehash: ae40d8adaae70ccff6e8058858a506267d58873f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133743"
---
# <a name="modulebindinfo-structure"></a>ModuleBindInfo 구조체
참조 된 모듈 및이 모듈을 포함 하는 어셈블리에 대 한 자세한 정보를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct _ModuleBindInfo {  
    DWORD    dwAppDomainId;  
    LPCWSTR  lpAssemblyIdentity;  
    LPCWSTR  lpModuleName  
} ModuleBindInfo;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`dwAppDomainId`|참조 된 모듈을 로드할 [IHostAssemblyStore::P rovidemodule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) 메서드를 호출 하 여 반환 되는 `IStream`에 대 한 고유 식별자입니다.|  
|`lpAssemblyIdentity`|참조 된 모듈이 포함 된 어셈블리에 대 한 고유 식별자입니다.|  
|`lpModuleName`|참조 된 모듈의 이름입니다.|  
  
## <a name="remarks"></a>주의  
 `ModuleBindInfo`는 `IHostAssemblyStore::ProvideModule`에 대 한 매개 변수로 전달 됩니다. 호스트는 CLR (공용 언어 런타임)에 `dwAppDomainId` 고유 식별자를 제공 합니다. [IHostAssemblyStore::P rovideassembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) 메서드에 대 한 호출이 반환 된 후에는 런타임에서 식별자를 사용 하 여 `IStream` 내용이 매핑되는지 여부를 확인 합니다. 이 경우 런타임은 스트림을 다시 매핑하지 않고 기존 복사본을 로드 합니다. 또한 런타임은 `IHostAssemblyStore::ProvideAssembly` 메서드에 대 한 호출에서 반환 되는 스트림의 조회 키로이 식별자를 사용 합니다. 따라서 식별자는 어셈블리 요청 뿐만 아니라 모듈 요청에 대해서만 고유 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [호스팅 구조체](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [AssemblyBindInfo 구조체](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)
- [ICLRAssemblyIdentityManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [ICLRAssemblyReferenceList 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
