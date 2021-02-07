---
description: '자세히 알아보기: IHostSecurityManager:: ImpersonateLoggedOnUser 메서드'
title: IHostSecurityManager::ImpersonateLoggedOnUser 메서드
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.ImpersonateLoggedOnUser
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::ImpersonateLoggedOnUser
helpviewer_keywords:
- ImpersonateLoggedOnUser method [.NET Framework hosting]
- IHostSecurityManager::ImpersonateLoggedOnUser method [.NET Framework hosting]
ms.assetid: acc49ba0-f1d9-45ad-871f-9d053a89dcbe
topic_type:
- apiref
ms.openlocfilehash: 7b77e0a163551a48629898b1311fc19ba815aaf4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671596"
---
# <a name="ihostsecuritymanagerimpersonateloggedonuser-method"></a>IHostSecurityManager::ImpersonateLoggedOnUser 메서드

현재 사용자 id의 자격 증명을 사용 하 여 코드를 실행 하도록 요청 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ImpersonateLoggedOnUser (  
    [in] HANDLE hToken  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `hToken`  
 진행 가장할 사용자의 자격 증명을 나타내는 토큰입니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`ImpersonateLoggedOnUser` 성공적으로 반환 되었습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
  
## <a name="remarks"></a>설명  

 `LogonUser`또는 관련 Win32 함수를 호출 하 여 현재 사용자 id의 자격 증명에 대 한 핸들을 가져옵니다.  
  
 `HANDLE`형식이 COM 규격이 아닙니다. 즉, 해당 크기는 운영 체제에 따라 달라 지 며 사용자 지정 마샬링이 필요 합니다. 따라서이 토큰은 프로세스 내 에서만 사용 되 고 CLR과 호스트 사이에 사용 됩니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IHostSecurityContext 인터페이스](ihostsecuritycontext-interface.md)
- [IHostSecurityManager 인터페이스](ihostsecuritymanager-interface.md)
- [RevertToSelf 메서드](ihostsecuritymanager-reverttoself-method.md)
