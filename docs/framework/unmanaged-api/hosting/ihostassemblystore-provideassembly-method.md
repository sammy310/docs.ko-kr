---
title: IHostAssemblyStore::ProvideAssembly 메서드
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore.ProvideAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore::ProvideAssembly
helpviewer_keywords:
- ProvideAssembly method [.NET Framework hosting]
- IHostAssemblyStore::ProvideAssembly method [.NET Framework hosting]
ms.assetid: 625c3dd5-a3f0-442c-adde-310dadbb5054
topic_type:
- apiref
ms.openlocfilehash: a93d700c9c398076d87156cd2eb9c6d0d08cccfd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124483"
---
# <a name="ihostassemblystoreprovideassembly-method"></a>IHostAssemblyStore::ProvideAssembly 메서드
[IHostAssemblyManager:: GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)에서 반환 된 [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) 에서 참조 하지 않는 어셈블리에 대 한 참조를 가져옵니다. CLR (공용 언어 런타임)은 목록에 표시 되지 않는 각 어셈블리에 대 한 `ProvideAssembly`를 호출 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ProvideAssembly (  
    [in]  AssemblyBindInfo *pBindInfo,  
    [out] UINT64           *pAssemblyId,  
    [out] UINT64           *pHostContext,  
    [out] IStream          **ppStmAssemblyImage,  
    [out] IStream          **ppStmPDB  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pBindInfo`  
 진행 호스트에서 버전 관리 정책 유무를 비롯 하 여 특정 바인딩 특성을 확인 하는 데 사용 하는 [Assemblybindinfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md) 인스턴스에 대 한 포인터와 바인딩할 어셈블리입니다.  
  
 `pAssemblyId`  
 제한이 이 `IStream`에 대해 요청 된 어셈블리의 고유 식별자에 대 한 포인터입니다.  
  
 `pHostContext`  
 제한이 플랫폼 호출이 없어도 요청 된 어셈블리의 증명 정보를 확인 하는 데 사용 되는 호스트 관련 데이터에 대 한 포인터입니다. `pHostContext`는 관리 되는 <xref:System.Reflection.Assembly> 클래스의 <xref:System.Reflection.Assembly.HostContext%2A> 속성에 해당 합니다.  
  
 `ppStmAssemblyImage`  
 제한이 로드할 PE (이식 가능한 실행) 이미지를 포함 하는 `IStream`의 주소에 대 한 포인터 이거나, 어셈블리를 찾을 수 없는 경우 null입니다.  
  
 `ppStmPDB`  
 제한이 PDB (프로그램 디버그) 정보를 포함 하는 `IStream`의 주소에 대 한 포인터 이거나 .pdb 파일을 찾을 수 없는 경우 null입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`ProvideAssembly` 성공적으로 반환 되었습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다. 호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.|  
|COR_E_FILENOTFOUND (0x80070002)|요청 된 어셈블리를 찾을 수 없습니다.|  
|E_NOT_SUFFICIENT_BUFFER|`pAssemblyId`로 지정 된 버퍼 크기가 호스트에서 반환 하려는 식별자를 저장할 만큼 크지 않습니다.|  
  
## <a name="remarks"></a>주의  
 `pAssemblyId`에 대해 반환 되는 id 값은 호스트에서 지정 합니다. 식별자는 프로세스의 수명 내에서 고유 해야 합니다. CLR은이 값을 스트림의 고유 식별자로 사용 합니다. `ProvideAssembly`에 대 한 다른 호출에서 반환 된 `pAssemblyId` 값에 대해 각 값을 검사 합니다. 호스트에서 다른 `IStream`에 대해 동일한 `pAssemblyId` 값을 반환 하는 경우 CLR은 해당 스트림의 내용이 이미 매핑 되었는지 여부를 확인 합니다. 이 경우 런타임에서는 새 이미지를 매핑하는 대신 이미지의 기존 복사본을 로드 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRAssemblyReferenceList 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [IHostAssemblyStore 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
