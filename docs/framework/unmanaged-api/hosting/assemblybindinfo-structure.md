---
description: 다음에 대해 자세히 알아보세요. AssemblyBindInfo 구조체
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
ms.openlocfilehash: 3e11e05924ee6818737f84d9ca92394ee5313292
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799982"
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
  
## <a name="members"></a>구성원  
  
|멤버|설명|  
|------------|-----------------|  
|`dwAppDomainId`|`IStream`참조 된 어셈블리를 로드할 [IHostAssemblyStore::P rovideassembly](ihostassemblystore-provideassembly-method.md)에 대 한 호출에서 반환 된의 고유 식별자입니다.|  
|`lpReferencedIdentity`|참조 된 어셈블리에 대 한 고유 식별자입니다.|  
|`lpPostPolicyIdentity`|바인딩 정책 값을 적용 한 후 참조 된 어셈블리의 식별자입니다.|  
|`ePolicyLevel`|참조 된 어셈블리에 적용 해야 하는 버전 관리 정책 (있는 경우)을 나타내는 [EPolicyAction](epolicyaction-enumeration.md) 값 중 하나입니다.|  
  
## <a name="remarks"></a>설명  

 호스트는 `dwAppDomainId` CLR (공용 언어 런타임)에 고유 식별자를 제공 합니다. 에 대 한 호출이 `IHostAssemblyStore::ProvideAssembly` 반환 된 후 런타임은 식별자를 사용 하 여의 내용이 매핑 되었는지 여부를 확인 합니다 `IStream` . 이 경우 런타임은 스트림을 다시 매핑하지 않고 기존 복사본을 로드 합니다. 또한 런타임은 [IHostAssemblyStore::P rovidemodule](ihostassemblystore-providemodule-method.md)에 대 한 호출에서 반환 되는 스트림의 조회 키로이 식별자를 사용 합니다. 따라서 식별자는 모듈 요청 및 어셈블리 요청에 대해 고유 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [호스팅 구조체](hosting-structures.md)
- [ICLRAssemblyIdentityManager 인터페이스](iclrassemblyidentitymanager-interface.md)
- [ICLRAssemblyReferenceList 인터페이스](iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager 인터페이스](ihostassemblymanager-interface.md)
- [IHostAssemblyStore 인터페이스](ihostassemblystore-interface.md)
- [ModuleBindInfo 구조체](modulebindinfo-structure.md)
