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
ms.openlocfilehash: f97490e89e835716911072dbad5f70d8e55e76e6
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805024"
---
# <a name="ihostassemblystoreprovideassembly-method"></a>IHostAssemblyStore::ProvideAssembly 메서드
[IHostAssemblyManager:: GetNonHostStoreAssemblies](ihostassemblymanager-getnonhoststoreassemblies-method.md)에서 반환 된 [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) 에서 참조 하지 않는 어셈블리에 대 한 참조를 가져옵니다. CLR (공용 언어 런타임)은 `ProvideAssembly` 목록에 표시 되지 않는 각 어셈블리에 대해를 호출 합니다.  
  
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
 진행 호스트에서 버전 관리 정책 유무를 비롯 하 여 특정 바인딩 특성을 확인 하는 데 사용 하는 [Assemblybindinfo](assemblybindinfo-structure.md) 인스턴스에 대 한 포인터와 바인딩할 어셈블리입니다.  
  
 `pAssemblyId`  
 제한이 이의 요청 된 어셈블리에 대 한 고유 식별자에 대 한 포인터 `IStream` 입니다.  
  
 `pHostContext`  
 제한이 플랫폼 호출이 없어도 요청 된 어셈블리의 증명 정보를 확인 하는 데 사용 되는 호스트 관련 데이터에 대 한 포인터입니다. `pHostContext`<xref:System.Reflection.Assembly.HostContext%2A>관리 되는 클래스의 속성에 해당 <xref:System.Reflection.Assembly> 합니다.  
  
 `ppStmAssemblyImage`  
 제한이 `IStream`로드할 PE (이식 가능한 실행) 이미지를 포함 하는의 주소에 대 한 포인터 이거나, 어셈블리를 찾을 수 없는 경우 null입니다.  
  
 `ppStmPDB`  
 제한이 `IStream`Pdb (프로그램 디버그) 정보를 포함 하는의 주소에 대 한 포인터 이거나 .pdb 파일을 찾을 수 없는 경우 null입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|`ProvideAssembly`성공적으로 반환 되었습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
|COR_E_FILENOTFOUND (0x80070002)|요청 된 어셈블리를 찾을 수 없습니다.|  
|E_NOT_SUFFICIENT_BUFFER|로 지정 된 버퍼 크기가 `pAssemblyId` 호스트에서 반환 하려는 식별자를 보유할 만큼 크지 않은 경우|  
  
## <a name="remarks"></a>설명  
 에 대해 반환 된 id 값은 `pAssemblyId` 호스트에서 지정 합니다. 식별자는 프로세스의 수명 내에서 고유 해야 합니다. CLR은이 값을 스트림의 고유 식별자로 사용 합니다. 이 메서드는에 대 한 `pAssemblyId` 다른 호출에서 반환 된 값을 기준으로 각 값을 검사 `ProvideAssembly` 합니다. 호스트에서 다른 값을 반환 하는 경우 `pAssemblyId` `IStream` CLR은 해당 스트림의 내용이 이미 매핑 되었는지 여부를 확인 합니다. 이 경우 런타임에서는 새 이미지를 매핑하는 대신 이미지의 기존 복사본을 로드 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRAssemblyReferenceList 인터페이스](iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager 인터페이스](ihostassemblymanager-interface.md)
- [IHostAssemblyStore 인터페이스](ihostassemblystore-interface.md)
