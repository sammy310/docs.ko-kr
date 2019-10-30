---
title: IHostSecurityManager::OpenThreadToken 메서드
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.OpenThreadToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::OpenThreadToken
helpviewer_keywords:
- IHostSecurityManager::OpenThreadToken method [.NET Framework hosting]
- OpenThreadToken method [.NET Framework hosting]
ms.assetid: d5999052-8bf0-4a9e-8621-da6284406b18
topic_type:
- apiref
ms.openlocfilehash: 2ced153798355aff882f0244f3dd946c39dea2bd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121464"
---
# <a name="ihostsecuritymanageropenthreadtoken-method"></a>IHostSecurityManager::OpenThreadToken 메서드
현재 실행 중인 스레드와 연결 된 임의 액세스 토큰을 엽니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT OpenThreadToken (  
    [in]  DWORD    dwDesiredAccess,   
    [in]  BOOL     bOpenAsSelf,   
    [out] HANDLE   *phThreadToken  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `dwDesiredAccess`  
 진행 스레드 토큰에 대 한 요청 된 액세스 형식을 지정 하는 액세스 값의 마스크입니다. 이러한 값은 Win32 `OpenThreadToken` 함수에서 정의 됩니다. 요청 된 액세스 형식은 토큰의 DACL (임의 액세스 제어 목록)과 비교 하 여 부여 하거나 거부할 액세스 형식을 결정 합니다.  
  
 `bOpenAsSelf`  
 [in] 호출 스레드에 대 한 프로세스의 보안 컨텍스트를 사용 하 여 액세스 검사를 수행 하도록 지정 하려면 `true` 합니다. 호출 하는 스레드에 대 한 보안 컨텍스트를 사용 하 여 액세스 검사를 수행 하도록 지정 하려면 `false` 합니다. 스레드가 클라이언트를 가장 하는 경우 보안 컨텍스트는 클라이언트 프로세스의 컨텍스트가 될 수 있습니다.  
  
 `phThreadToken`  
 제한이 새로 열린 액세스 토큰에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`OpenThreadToken` 성공적으로 반환 되었습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다. 호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.|  
  
## <a name="remarks"></a>주의  
 `IHostSecurityManager::OpenThreadToken`는 Win32 함수를 사용 하 여 호출자가 임의 스레드에 대 한 핸들을 전달할 수 있는 반면 `IHostSecurityManager::OpenThreadToken`는 호출 스레드와 연결 된 토큰만 여는 것을 제외 하 고는 동일한 이름의 해당 Win32 함수와 비슷하게 동작 합니다.  
  
 `HANDLE` 형식은 COM 규격이 아닙니다. 즉, 크기는 운영 체제에 따라 달라 지 며 사용자 지정 마샬링이 필요 합니다. 따라서이 토큰은 프로세스 내 에서만 사용 되 고 CLR과 호스트 사이에 사용 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [IHostSecurityContext 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [IHostSecurityManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
