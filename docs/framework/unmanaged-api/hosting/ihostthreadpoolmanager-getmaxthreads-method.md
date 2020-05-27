---
title: IHostThreadPoolManager::GetMaxThreads 메서드
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetMaxThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMaxThreads method [.NET Framework hosting]
- GetMaxThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: db268876-6178-4a81-aca3-318ee7f96001
topic_type:
- apiref
ms.openlocfilehash: efbfa310c90f48c99219cb185f090a1b854949a2
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842285"
---
# <a name="ihostthreadpoolmanagergetmaxthreads-method"></a>IHostThreadPoolManager::GetMaxThreads 메서드
호스트가 스레드 풀에서 동시에 유지 관리 하는 최대 스레드 수를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxWorkerThreads  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pdwMaxWorkerThreads`  
 제한이 호스트가 스레드 풀에서 유지 관리 하는 최대 스레드 수에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|`GetMaxThreads`성공적으로 반환 되었습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
|E_NOTIMPL|호스트는의 구현을 제공 하지 않습니다 `GetMaxThreads` .|  
  
## <a name="remarks"></a>설명  
 CLR은 `GetMaxThreads` 를 호출 하 여 스레드 풀의 총 스레드 수를 확인 합니다. [Get사용할](ihostthreadpoolmanager-getavailablethreads-method.md) 수 있는 threads 메서드는 현재 작업 항목을 처리 하 고 있지 않은 스레드 수를 가져옵니다. 반환 된 매개 변수의 값을 초과 하는 모든 요청은 `pdwMaxWorkerThreads` 스레드를 사용할 수 있을 때까지 큐에 유지 됩니다.  
  
 호스트에서의 구현을 제공 하지 않는 경우 `GetMaxThreads` E_NOTIMPL HRESULT 값을 반환 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Threading.ThreadPool.GetMaxThreads%2A>
- <xref:System.Threading.ThreadPool>
- [GetMinThreads 메서드](ihostthreadpoolmanager-getminthreads-method.md)
- [SetMaxThreads 메서드](ihostthreadpoolmanager-setmaxthreads-method.md)
- [IHostThreadPoolManager 인터페이스](ihostthreadpoolmanager-interface.md)
