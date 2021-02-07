---
description: '자세히 알아보기: IHostSecurityManager:: SetSecurityContext 메서드'
title: IHostSecurityManager::SetSecurityContext 메서드
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.SetSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::SetSecurityContext
helpviewer_keywords:
- SetSecurityContext method [.NET Framework hosting]
- IHostSecurityManager::SetSecurityContext method [.NET Framework hosting]
ms.assetid: e4372384-ee69-48d7-97e0-8fab7866597a
topic_type:
- apiref
ms.openlocfilehash: ee2de40e043e626aba1d75540faab3cae4c8fb7e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671479"
---
# <a name="ihostsecuritymanagersetsecuritycontext-method"></a>IHostSecurityManager::SetSecurityContext 메서드

현재 실행 중인 스레드의 보안 컨텍스트를 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetSecurityContext (  
    [in]  EContextType eContextType,  
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `eContextType`  
 진행 CLR (공용 언어 런타임)이 호스트에 배치 하는 컨텍스트 유형을 나타내는 [EContextType](econtexttype-enumeration.md) 값 중 하나입니다.  
  
 `ppSecurityContext`  
 제한이 새 [IHostSecurityContext](ihostsecuritycontext-interface.md) 개체의 주소에 대 한 포인터입니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`SetSecurityContext` 성공적으로 반환 되었습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
  
## <a name="remarks"></a>설명  

 CLR은 `SetSecurityContext` 여러 시나리오에서를 호출 합니다. CLR은 클래스 및 모듈 생성자와 종료자를 실행 하기 전에 `SetSecurityContext` 를 호출 하 여 호스트를 실행 오류 로부터 보호 합니다. 그런 다음에 대 한 다른 호출을 사용 하 여 생성자 또는 종료자를 실행 한 후 보안 컨텍스트를 원래 상태로 다시 설정 `SetSecurityContext` 합니다. I/o가 완료 되 면 비슷한 패턴이 발생 합니다. 호스트가 [IHostIoCompletionManager](ihostiocompletionmanager-interface.md)를 구현 하는 경우 CLR은 `SetSecurityContext` [Iclrio manager:: OnComplete](iclriocompletionmanager-oncomplete-method.md)를 호출한 후를 호출 합니다.  
  
 작업자 스레드의 비동기 지점에서 CLR은 `SetSecurityContext` <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> 호스트나 clr이 스레드 풀을 구현 하 고 있는지 여부에 따라 [IHostThreadPoolManager:: QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md)내에서 또는 내에서를 호출 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Threading.ThreadPool?displayProperty=nameWithType>
- [EContextType 열거형](econtexttype-enumeration.md)
- [ICLRIoCompletionManager 인터페이스](iclriocompletionmanager-interface.md)
- [IHostIoCompletionManager 인터페이스](ihostiocompletionmanager-interface.md)
- [IHostSecurityContext 인터페이스](ihostsecuritycontext-interface.md)
- [IHostSecurityManager 인터페이스](ihostsecuritymanager-interface.md)
- [IHostThreadPoolManager 인터페이스](ihostthreadpoolmanager-interface.md)
