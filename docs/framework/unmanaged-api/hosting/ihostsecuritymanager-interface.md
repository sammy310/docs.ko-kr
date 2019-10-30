---
title: IHostSecurityManager 인터페이스
ms.date: 03/30/2017
api_name:
- IHostSecurityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager
helpviewer_keywords:
- IHostSecurityManager interface [.NET Framework hosting]
ms.assetid: c3be2cbd-2d93-438b-9888-9a0251b63c03
topic_type:
- apiref
ms.openlocfilehash: 9b7cc41848e41976f388e38bf22c9ea0f90abbae
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121487"
---
# <a name="ihostsecuritymanager-interface"></a>IHostSecurityManager 인터페이스
현재 실행 중인 스레드의 보안 컨텍스트에 대 한 액세스 및 제어를 허용 하는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetSecurityContext 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)|호스트에서 요청 된 [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) 를 가져옵니다.|  
|[ImpersonateLoggedOnUser 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)|현재 사용자 id의 자격 증명을 사용 하 여 코드를 실행 하도록 요청 합니다.|  
|[OpenThreadToken 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-openthreadtoken-method.md)|현재 스레드와 연결 된 임의 액세스 토큰을 엽니다.|  
|[RevertToSelf 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)|현재 사용자 id의 가장을 종료 하 고 원래 스레드 토큰을 반환 합니다.|  
|[SetSecurityContext 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md)|현재 실행 중인 스레드에 대 한 보안 컨텍스트를 설정 합니다.|  
|[SetThreadToken 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setthreadtoken-method.md)|현재 실행 중인 스레드에 대 한 핸들을 설정 합니다.|  
  
## <a name="remarks"></a>주의  
 호스트는 CLR (공용 언어 런타임) 및 사용자 코드를 모두 사용 하 여 스레드 토큰에 대 한 모든 코드 액세스를 제어할 수 있습니다. 또한 코드 액세스가 제한 된 비동기 작업 또는 코드 포인트로 전체 보안 컨텍스트 정보를 전달 하도록 할 수 있습니다. `IHostSecurityContext`는 CLR에 불투명 한이 보안 컨텍스트 정보를 캡슐화 합니다.  
  
 CLR은 내부적으로 관리 되는 스레드 컨텍스트를 처리 합니다. 다음과 같은 상황에서 프로세스 관련 `IHostSecurityManager`을 쿼리 합니다.  
  
- 종료자 스레드에서 종료자를 실행 하는 동안  
  
- 클래스 및 모듈 생성자를 실행 하는 동안  
  
- 작업자 스레드의 비동기 지점에서 [IHostThreadPoolManager:: QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md) 메서드를 호출 합니다.  
  
- I/o 완료 포트의 서비스를 제공 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [IHostSecurityContext 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
