---
title: AssemblyBindInfo 구조체
ms.date: 03/30/2017
api_name:
- AssemblyBindInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyBindInfo
helpviewer_keywords:
- AssemblyBindInfo structure [.NET Framework hosting]
ms.assetid: 6fc01e98-c2e7-49de-ab9f-95937cc89017
topic_type:
- apiref
ms.openlocfilehash: 8764a3d665c997460419561eb168f92ca769c30c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192106"
---
# <a name="assemblybindinfo-structure"></a>AssemblyBindInfo 구조체
참조 된 어셈블리에 대 한 자세한 정보를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct _AssemblyBindInfo {  
    DWORD       dwAppDomainId;  
    LPCWSTR     lpReferencedIdentity;  
    LPCWSTR     lpPostPolicyIdentity;  
    DWORD       ePolicyLevel;  
} AssemblyBindInfo;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`dwAppDomainId`|참조 된 어셈블리를 로드할 [IHostAssemblyStore::P rovideassembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)에 대 한 호출에서 반환 되는 `IStream`에 대 한 고유 식별자입니다.|  
|`lpReferencedIdentity`|참조 된 어셈블리에 대 한 고유 식별자입니다.|  
|`lpPostPolicyIdentity`|바인딩 정책 값을 적용 한 후 참조 된 어셈블리의 식별자입니다.|  
|`ePolicyLevel`|참조 된 어셈블리에 적용 해야 하는 버전 관리 정책 (있는 경우)을 나타내는 [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) 값 중 하나입니다.|  
  
## <a name="remarks"></a>주의  
 호스트는 CLR (공용 언어 런타임)에 `dwAppDomainId` 고유 식별자를 제공 합니다. `IHostAssemblyStore::ProvideAssembly`에 대 한 호출이 반환 된 후 런타임에서는 식별자를 사용 하 여 `IStream` 내용이 매핑되는지 여부를 확인 합니다. 이 경우 런타임은 스트림을 다시 매핑하지 않고 기존 복사본을 로드 합니다. 또한 런타임은 [IHostAssemblyStore::P rovidemodule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)에 대 한 호출에서 반환 되는 스트림의 조회 키로이 식별자를 사용 합니다. 따라서 식별자는 모듈 요청 및 어셈블리 요청에 대해 고유 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [호스팅 구조체](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [ICLRAssemblyIdentityManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [ICLRAssemblyReferenceList 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [IHostAssemblyStore 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [ModuleBindInfo 구조체](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md)
