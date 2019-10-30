---
title: IHostAssemblyStore::ProvideModule 메서드
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore.ProvideModule
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore::ProvideModule
helpviewer_keywords:
- IHostAssemblyStore::ProvideModule method [.NET Framework hosting]
- ProvideModule method [.NET Framework hosting]
ms.assetid: f42e3dd0-c88e-4748-b6c0-4c515a633180
topic_type:
- apiref
ms.openlocfilehash: eed09a8149a21140ad61133f29391f86cb0fb929
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124467"
---
# <a name="ihostassemblystoreprovidemodule-method"></a>IHostAssemblyStore::ProvideModule 메서드
어셈블리 또는 연결 된 (포함 된) 리소스 파일 내에서 모듈을 확인 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pBindInfo`  
 진행 요청 된 모듈의 <xref:System.AppDomain>, 어셈블리 및 모듈 이름을 설명 하는 [Modulebindinfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) 인스턴스에 대 한 포인터입니다.  
  
 `pdwModuleId`  
 제한이 로드 된 모듈을 포함 하는 `IStream`에 대 한 고유 식별자에 대 한 포인터입니다.  
  
 `ppStmModuleImage`  
 제한이 로드할 PE (이식 가능한 실행) 이미지를 포함 하는 `IStream` 개체의 주소에 대 한 포인터 이거나, 모듈을 찾을 수 없는 경우 null입니다.  
  
 `ppStmPDB`  
 제한이 요청 된 모듈의 PDB (프로그램 디버그) 정보를 포함 하는 `IStream` 개체의 주소에 대 한 포인터 이거나 .pdb 파일을 찾을 수 없는 경우 null입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`ProvideModule` 성공적으로 반환 되었습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다. 호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.|  
|COR_E_FILENOTFOUND (0x80070002)|요청 된 어셈블리 또는 링크 된 리소스를 찾을 수 없습니다.|  
|E_NOT_SUFFICIENT_BUFFER|`pdwModuleId` 호스트에서 반환 하려는 식별자를 포함 하기에 충분 하지 않습니다.|  
  
## <a name="remarks"></a>주의  
 `pdwModuleId`에 대해 반환 되는 id 값은 호스트에서 지정 합니다. 식별자는 프로세스의 수명 내에서 고유 해야 합니다. CLR은이 값을 연결 된 스트림에 대 한 고유 식별자로 사용 합니다. [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) 에 대 한 호출에 의해 반환 되는 `pAssemblyId`의 값과 `ProvideModule`에 대 한 다른 호출에서 반환 된 `pdwModuleId`의 값을 비교 하 여 각 값을 확인 합니다. 호스트에서 다른 `IStream`에 대해 동일한 id 값을 반환 하는 경우 CLR은 해당 스트림의 내용이 이미 매핑 되었는지 여부를 확인 합니다. 그렇다면 CLR은 새 이미지를 매핑하는 대신 이미지의 기존 복사본을 로드 합니다. 따라서 식별자는 `ProvideAssembly`에서 반환 된 어셈블리 식별자와 겹치면 안 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRAssemblyReferenceList 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [IHostAssemblyStore 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
