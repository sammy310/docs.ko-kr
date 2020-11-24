---
title: IHostIoCompletionManager::GetMinThreads 메서드
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetMinThreads
helpviewer_keywords:
- GetMinThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::GetMinThreads method [.NET Framework hosting]
ms.assetid: d7a7f733-677d-481c-b3d5-444fcc502b8e
topic_type:
- apiref
ms.openlocfilehash: d321ce08edf4780fc5f26ac627849b9129c2f283
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673230"
---
# <a name="ihostiocompletionmanagergetminthreads-method"></a>IHostIoCompletionManager::GetMinThreads 메서드

호스트에서 i/o 요청을 처리 하기 위해 제공 하는 최소 스레드 수를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetMinThreads (  
    [out] DWORD *pdwMinIOCompletionThreads  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pdwMinIOCompletionThreads`  
 제한이 호스트에서 i/o 요청을 처리 하기 위해 제공 하는 최소 스레드 수에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`GetMinThreads` 성공적으로 반환 되었습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
|E_NOTIMPL|호스트는의 구현을 제공 하지 않습니다 `GetMinThreads` .|  
  
## <a name="remarks"></a>설명  

 호스트는 구현, 성능 또는 확장성과 같은 이유로 서비스 i/o 요청에 할당 된 스레드 수에 대 한 배타적 제어를 원할 수 있습니다. 따라서 호스트는를 구현할 필요가 없습니다 `GetMinThreads` . 이 경우 호스트는이 메서드에서 E_NOTIMPL을 반환 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRIoCompletionManager 인터페이스](iclriocompletionmanager-interface.md)
- [IHostIoCompletionManager 인터페이스](ihostiocompletionmanager-interface.md)
