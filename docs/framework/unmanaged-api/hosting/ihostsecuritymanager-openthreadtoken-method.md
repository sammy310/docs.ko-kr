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
ms.openlocfilehash: 11d042ea9eecc8d428761da6eaa15f7c2907ebd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176268"
---
# <a name="ihostsecuritymanageropenthreadtoken-method"></a>IHostSecurityManager::OpenThreadToken 메서드
현재 실행 중인 스레드와 연결된 임의 액세스 토큰을 엽니다.  
  
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
 【인】 스레드 토큰에 대한 요청된 액세스 유형을 지정하는 액세스 값의 마스크입니다. 이러한 값은 Win32 `OpenThreadToken` 함수에 정의되어 있습니다. 요청된 액세스 형식은 토큰의 임의 액세스 제어 목록(DACL)과 조정되어 부여 또는 거부에 대한 액세스 유형을 결정합니다.  
  
 `bOpenAsSelf`  
 【인】 `true` 호출 스레드에 대한 프로세스의 보안 컨텍스트를 사용하여 액세스 검사를 수행해야 하도록 지정합니다. `false` 을 사용하 여 호출 스레드 자체에 대 한 보안 컨텍스트를 사용 하 여 액세스 검사를 수행 해야 합니다 지정 합니다. 스레드가 클라이언트를 가장하는 경우 보안 컨텍스트는 클라이언트 프로세스의 컨텍스트일 수 있습니다.  
  
 `phThreadToken`  
 【아웃】 새로 열린 액세스 토큰에 대한 포인터입니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|`OpenThreadToken`성공적으로 반환됩니다.|  
|HOST_E_CLRNOTAVAILABLE|공통 언어 런타임(CLR)이 프로세스에 로드되지 않았거나 CLR이 관리 코드를 실행하거나 호출을 성공적으로 처리할 수 없는 상태입니다.|  
|HOST_E_TIMEOUT|통화 시간이 시간 미정으로 확인되었습니다.|  
|HOST_E_NOT_OWNER|호출자는 잠금을 소유하지 않습니다.|  
|HOST_E_ABANDONED|차단된 스레드 또는 파이버가 대기하는 동안 이벤트가 취소되었습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생했습니다. 메서드가 E_FAIL 반환하면 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다. 호스팅 메서드에 대한 후속 호출은 HOST_E_CLRNOTAVAILABLE 반환합니다.|  
  
## <a name="remarks"></a>설명  
 `IHostSecurityManager::OpenThreadToken`Win32 함수를 사용하면 호출자가 임의의 스레드에 핸들을 전달할 수 있지만 호출 스레드와 연결된 토큰만 `IHostSecurityManager::OpenThreadToken` 열린다는 점을 제외하면 동일한 이름의 해당 Win32 함수와 유사하게 작동합니다.  
  
 형식은 `HANDLE` COM을 준수하지 않으며, 즉 크기는 운영 체제에 따라 다르며 사용자 지정 마샬링이 필요합니다. 따라서 이 토큰은 CLR과 호스트 간의 프로세스 내에서만 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MSCorE.h  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IHostSecurityContext 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [IHostSecurityManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
