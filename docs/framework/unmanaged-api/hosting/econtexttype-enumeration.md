---
title: EContextType 열거형
ms.date: 03/30/2017
api_name:
- EContextType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EContextType
helpviewer_keywords:
- EContextType enumeration [.NET Framework hosting]
ms.assetid: 92b926a9-b87e-408a-9036-df7b752c9492
topic_type:
- apiref
ms.openlocfilehash: 5e82f542bdc364a52fc558e582134a7d8d554ec3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131152"
---
# <a name="econtexttype-enumeration"></a>EContextType 열거형
현재 실행 중인 스레드의 보안 컨텍스트를 설명 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum {  
    eCurrentContext    = 0x00,  
    eRestrictedContext = 0x01  
} EContextType;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`eCurrentContext`|CLR (공용 언어 런타임)이 [IHostSecurityManager:: GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) 메서드를 호출할 때 또는 [IHostSecurityManager:: SETSECURITYCONTEXT 호출에서 clr이 요청한 컨텍스트를 호출할 때 현재 스레드의 컨텍스트를 나타냅니다. ](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md)메서드.|  
|`eRestrictedContext`|호스트에 가비지 수집기, 클래스 또는 모듈 생성자 등의 낮은 권한이 있는 컨텍스트를 나타냅니다.|  
  
## <a name="remarks"></a>주의  
 CLR은 `IHostSecurityManager::GetSecurityContext` 및 `IHostSecurityManager::SetSecurityContext` 메서드에 대 한 호출에서 `EContextType` 값 중 하나를 매개 변수 값으로 제공 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [IHostSecurityContext 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [IHostSecurityManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [호스팅 열거형](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
