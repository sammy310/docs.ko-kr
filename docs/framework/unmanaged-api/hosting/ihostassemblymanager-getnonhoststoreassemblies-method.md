---
title: IHostAssemblyManager::GetNonHostStoreAssemblies 메서드
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager.GetNonHostStoreAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager::GetNonHostStoreAssemblies
helpviewer_keywords:
- IHostAssemblyManager::GetNonHostStoreAssemblies method [.NET Framework hosting]
- GetNonHostStoreAssemblies method [.NET Framework hosting]
ms.assetid: d2250b38-c76a-40ce-80c8-ba45149886e8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3680721c70ab69776c973913d929f7bdd9db3909
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779452"
---
# <a name="ihostassemblymanagergetnonhoststoreassemblies-method"></a>IHostAssemblyManager::GetNonHostStoreAssemblies 메서드
한 인터페이스 포인터를 가져옵니다는 [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) 호스트에서 예상 하는 CLR (공용 언어 런타임)를 로드 하는 어셈블리의 목록을 나타내는입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetNonHostStoreAssemblies (  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `ppReferenceList`  
 [out] 주소에 대 한 포인터는 `ICLRAssemblyReferenceList` 호스트 로드 하기 위해 CLR에서 예상 하는 어셈블리에 대 한 참조의 목록을 포함 하는 합니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`GetNonHostStoreAssemblies` 성공적으로 반환 합니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다. 메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.|  
|E_OUTOFMEMORY|요청 된 작업에 대 한 참조 목록을 만드는 데 사용할 수 있는 메모리가 충분 하지 않습니다 `ICLRAssemblyReferenceList`합니다.|  
  
## <a name="remarks"></a>설명  
 다음 지침을 사용 하 여 참조를 확인 하는 CLR:  
  
- 반환 하는 어셈블리 참조의 목록을 확인 먼저 `GetNonHostStoreAssemblies`합니다.  
  
- 어셈블리 목록에 있으면 CLR에 정상적으로 바인딩합니다.  
  
- 어셈블리 목록에 나타나지 않습니다 하 고 호스트의 구현을 제공 했습니다 [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md), CLR 호출 [ihostassemblystore:: Provideassembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) 호스트가 제공 하는 바인딩할 어셈블리입니다.  
  
- 그렇지 않으면 CLR 어셈블리에 바인딩할 실패 합니다.  
  
 호스트 설정 하는 경우 `ppReferenceList` null이 고, CLR 첫 번째 프로브를 전역 어셈블리 캐시에는 다음과 같이 호출 됩니다. `ProvideAssembly`, 및 다음 어셈블리 참조를 확인 하는 응용 프로그램 기준 위치를 프로브 합니다.  
  
> [!NOTE]
>  초기화 하면 CLR은 호출 `GetNonHostStoreAssemblies` 한 번만 합니다. 메서드를 다시 호출 되지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [ICLRAssemblyReferenceList 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [IHostAssemblyStore 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
