---
title: ICLRAssemblyIdentityManager::GetBindingIdentityFromFile 메서드
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetBindingIdentityFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetBindingIdentityFromFile
helpviewer_keywords:
- GetBindingIdentityFromFile method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetBindingIdentifyFromFile method [.NET Framework hosting]
ms.assetid: 7797562d-7b4c-4bd9-8b93-f35e0e2869e4
topic_type:
- apiref
ms.openlocfilehash: 443acfa77dc8103008263f19bed116d02e7ea676
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716743"
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromfile-method"></a>ICLRAssemblyIdentityManager::GetBindingIdentityFromFile 메서드

지정 된 파일 경로에서 어셈블리의 어셈블리 id 바인딩 데이터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetBindingIdentityFromFile(  
    [in] LPCWSTR     pwzFilePath,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pwzFilePath`  
 진행 평가할 파일의 경로입니다.  
  
 `dwFlags`  
 진행 어셈블리의 id 유형을 나타내는 [ECLRAssemblyIdentityFlags](eclrassemblyidentityflags-enumeration.md) 열거형의 값입니다. 향후 확장성을 위해 제공 됩니다. CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT은 CLR (공용 언어 런타임) 버전 2.0에서 지 원하는 유일한 값입니다.  
  
 `pwzBuffer`  
 제한이 불투명 어셈블리 id 데이터를 포함 하는 버퍼입니다.  
  
 `pcchBufferSize`  
 [in, out] 의 크기에 대 한 포인터입니다 `pwzBuffer` .  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|메서드가 성공적으로 반환했습니다.|  
|E_INVALIDARG|제공 된 `pwzFilePath` 가 null 인 경우|  
|ERROR_INSUFFICIENT_BUFFER|의 크기가 `pwzBuffer` 너무 작습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
  
## <a name="remarks"></a>설명  

 `GetBindingIdentityFromFile` 는 일반적으로 두 번 호출 됩니다. 첫 번째 호출은에 null 값을 제공 `pwzBuffer` 하 고, 메서드는에서 적절 한 크기를 반환 합니다 `pcchBufferSize` . 두 번째 호출은 적절 하 게 할당 된 버퍼를 제공 하 고, 메서드는 완료 시 실제 버퍼 데이터와 함께를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRAssemblyIdentityManager 인터페이스](iclrassemblyidentitymanager-interface.md)
- [ICLRAssemblyReferenceList 인터페이스](iclrassemblyreferencelist-interface.md)
- [ICLRHostBindingPolicyManager 인터페이스](iclrhostbindingpolicymanager-interface.md)
