---
title: ICLRAssemblyIdentityManager::GetBindingIdentityFromStream 메서드
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetBindingIdentityFromStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetBindingIdentityFromStream
helpviewer_keywords:
- GetBindingIdentityFromStream method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetBindingIdentityFromStream method [.NET Framework hosting]
ms.assetid: 40123b30-a589-46b3-95d3-af7b2b0baa05
topic_type:
- apiref
ms.openlocfilehash: abba19600616cad8ba3377ae2ebb23459449d2a0
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615984"
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromstream-method"></a>ICLRAssemblyIdentityManager::GetBindingIdentityFromStream 메서드
지정 된 스트림의 어셈블리에 대 한 정식 어셈블리 id 데이터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetBindingIdentityFromStream (  
    [in] IStream    *pStream,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pStream`  
 진행 평가할 어셈블리 스트림입니다.  
  
 `dwFlags`  
 진행 향후 확장성을 위해 제공 됩니다. 현재 버전의 CLR (공용 언어 런타임)에서 지 원하는 유일한 값은 CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT입니다.  
  
 `pwzBuffer`  
 제한이 불투명 어셈블리 id 데이터를 포함 하는 버퍼입니다.  
  
 `pcchBufferSize`  
 [in, out] 의 크기 `pwzBuffer` 입니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|메서드가 성공적으로 반환했습니다.|  
|E_INVALIDARG|제공 된 `pStream` 가 null 인 경우|  
|ERROR_INSUFFICIENT_BUFFER|의 크기가 `pwzBuffer` 너무 작습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRAssemblyIdentityManager 인터페이스](iclrassemblyidentitymanager-interface.md)
- [ICLRAssemblyReferenceList 인터페이스](iclrassemblyreferencelist-interface.md)
