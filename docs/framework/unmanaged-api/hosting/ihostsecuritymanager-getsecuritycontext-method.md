---
title: IHostSecurityManager::GetSecurityContext 메서드
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.GetSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::GetSecurityContext
helpviewer_keywords:
- GetSecurityContext method [.NET Framework hosting]
- IHostSecurityManager::GetSecurityContext method [.NET Framework hosting]
ms.assetid: 958970d6-f6a2-4b84-b32a-f555cbaf8f61
topic_type:
- apiref
ms.openlocfilehash: 7198698edce48546c4f9a82ace18d5a6e71891ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176255"
---
# <a name="ihostsecuritymanagergetsecuritycontext-method"></a>IHostSecurityManager::GetSecurityContext 메서드
호스트에서 요청된 [IHostSecurityContext를](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetSecurityContext (  
    [in]  EContextType eContextType,
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `eContextType`  
 【인】 반환할 보안 컨텍스트 유형을 나타내는 [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) 값 중 하나입니다.  
  
 `ppSecurityContext`  
 【아웃】 의 인터페이스 포인터의 주소입니다. `IHostSecurityContext` `eContextType`  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|`GetSecurityContext`성공적으로 반환됩니다.|  
|HOST_E_CLRNOTAVAILABLE|공통 언어 런타임(CLR)이 프로세스에 로드되지 않았거나 CLR이 관리 코드를 실행하거나 호출을 성공적으로 처리할 수 없는 상태입니다.|  
|HOST_E_TIMEOUT|통화 시간이 시간 미정으로 확인되었습니다.|  
|HOST_E_NOT_OWNER|호출자는 잠금을 소유하지 않습니다.|  
|HOST_E_ABANDONED|차단된 스레드 또는 파이버가 대기하는 동안 이벤트가 취소되었습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생했습니다. 메서드가 E_FAIL 반환하면 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다. 호스팅 메서드에 대한 후속 호출은 HOST_E_CLRNOTAVAILABLE 반환합니다.|  
  
## <a name="remarks"></a>설명  
 호스트는 CLR 및 사용자 코드모두에서 스레드 토큰에 대한 모든 코드 액세스를 제어할 수 있습니다. 또한 전체 보안 컨텍스트 정보가 비동기 작업 또는 제한된 코드 액세스가 있는 코드 포인트에 전달되도록 할 수 있습니다. `IHostSecurityContext`이 보안 컨텍스트 정보를 캡슐화하며, 이는 CLR에 불투명합니다. CLR은 이 정보를 캡처하여 스레드 풀 작업자 항목 디스패치, 종료자 실행 및 모듈 및 클래스 구성을 통해 이동합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MSCorE.h  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [EContextType 열거형](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)
- [IHostSecurityContext 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [IHostSecurityManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
