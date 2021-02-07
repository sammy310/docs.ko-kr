---
description: '다음에 대 한 자세한 정보: ModuleBindInfo 구조체'
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
ms.openlocfilehash: 0969c0ecc459414336800e8e7da5817ac0c1a8ce
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679630"
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
  
## <a name="members"></a>구성원  
  
|멤버|설명|  
|------------|-----------------|  
|`dwAppDomainId`|`IStream`참조 된 모듈을 로드할 [IHostAssemblyStore::P rovidemodule](ihostassemblystore-providemodule-method.md) 메서드에 대 한 호출에서 반환 되는의 고유 식별자입니다.|  
|`lpAssemblyIdentity`|참조 된 모듈이 포함 된 어셈블리에 대 한 고유 식별자입니다.|  
|`lpModuleName`|참조 된 모듈의 이름입니다.|  
  
## <a name="remarks"></a>설명  

 `ModuleBindInfo` 는에 대 한 매개 변수로 전달 됩니다 `IHostAssemblyStore::ProvideModule` . 호스트는 `dwAppDomainId` CLR (공용 언어 런타임)에 고유 식별자를 제공 합니다. [IHostAssemblyStore::P rovideassembly](ihostassemblystore-provideassembly-method.md) 메서드에 대 한 호출이 반환 된 후 런타임은 식별자를 사용 하 여의 내용이 매핑 되었는지 여부를 확인 합니다 `IStream` . 이 경우 런타임은 스트림을 다시 매핑하지 않고 기존 복사본을 로드 합니다. 또한 런타임은 메서드 호출에서 반환 되는 스트림의 조회 키로이 식별자를 사용 합니다 `IHostAssemblyStore::ProvideAssembly` . 따라서 식별자는 어셈블리 요청 뿐만 아니라 모듈 요청에 대해서만 고유 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [호스팅 구조체](hosting-structures.md)
- [AssemblyBindInfo 구조체](assemblybindinfo-structure.md)
- [ICLRAssemblyIdentityManager 인터페이스](iclrassemblyidentitymanager-interface.md)
- [ICLRAssemblyReferenceList 인터페이스](iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager 인터페이스](ihostassemblymanager-interface.md)
