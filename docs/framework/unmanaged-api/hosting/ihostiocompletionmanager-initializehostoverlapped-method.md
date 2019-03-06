---
title: IHostIoCompletionManager::InitializeHostOverlapped 메서드
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.InitializeHostOverlapped
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped
helpviewer_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped method [.NET Framework hosting]
- InitializeHostOverlapped method [.NET Framework hosting]
ms.assetid: c35199bf-bc47-4901-b467-4e8a37644bbb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 97d2959a27bb848d05dc44492152866b2d535b68
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57503166"
---
# <a name="ihostiocompletionmanagerinitializehostoverlapped-method"></a>IHostIoCompletionManager::InitializeHostOverlapped 메서드
호스트 Win32에 추가할 사용자 지정 데이터를 초기화할 수 있도록 제공 `OVERLAPPED` 비동기 I/O 요청에 사용 되는 구조입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT InitializeHostOverlapped (  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pvOverlapped`  
 [in] Win32에 대 한 포인터 `OVERLAPPED` I/O 요청에 포함 되어야 하는 구조입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`InitializeHostOverlapped` 성공적으로 반환 합니다.|  
|HOST_E_CLRNOTAVAILABLE|프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다. 메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.|  
|E_OUTOFMEMORY|요청된 된 리소스를 할당할 수 있는 메모리가 부족 합니다.|  
  
## <a name="remarks"></a>설명  
 Windows 플랫폼을 사용 하 여 함수를 `OVERLAPPED` 비동기 I/O 요청에 대 한 상태를 저장 하는 구조입니다. CLR 호출 합니다 `InitializeHostOverlapped` 호스트에 사용자 지정 데이터를 추가할 수 있는 기회를 제공 하는 메서드는 `OVERLAPPED` 인스턴스.  
  
> [!IMPORTANT]
>  해당 사용자 지정 데이터 블록의 시작 부분에 연결할 호스트 설정 해야 오프셋의 크기를 `OVERLAPPED` 구조 (`sizeof(OVERLAPPED)`).  
  
 반환 값 e_outofmemory가 호스트에 해당 사용자 지정 데이터를 초기화 하지 못했음을 나타냅니다. 이 경우 CLR 오류를 보고 하 고 호출에 실패 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료
- [ICLRIoCompletionManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [GetHostOverlappedSize 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)
- [IHostIoCompletionManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
