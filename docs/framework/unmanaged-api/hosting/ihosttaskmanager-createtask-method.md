---
description: '자세히 알아보기: IHostTaskManager:: CreateTask 메서드'
title: IHostTaskManager::CreateTask 메서드
ms.date: 03/30/2017
api_name:
- IHostTaskManager.CreateTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::CreateTask
helpviewer_keywords:
- CreateTask method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::CreateTask method [.NET Framework hosting]
ms.assetid: a6f8ad36-61e1-42b0-9db2-add575646d18
topic_type:
- apiref
ms.openlocfilehash: c14c80ea9067b0a28e7b9186ea66eb695687bf27
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784576"
---
# <a name="ihosttaskmanagercreatetask-method"></a>IHostTaskManager::CreateTask 메서드

호스트에서 새 작업을 만들도록 요청 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CreateTask (  
    [in]  DWORD stacksize,
    [in]  LPTHREAD_START_ROUTINE pStartAddress,  
    [in]  PVOID pParameter,  
    [out] IHostTask **ppTask  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `stacksize`  
 진행 요청 된 스택의 요청 된 크기 (바이트) 이거나, 기본 크기의 경우 0입니다.  
  
 `pStartAddress`  
 진행 태스크가 실행 되는 함수에 대 한 포인터입니다.  
  
 `pParameter`  
 진행 함수에 전달 될 사용자 데이터에 대 한 포인터 이거나, 함수에서 매개 변수를 사용 하지 않는 경우 null입니다.  
  
 `ppTask`  
 제한이 호스트에서 만든 [IHostTask](ihosttask-interface.md) 인스턴스의 주소에 대 한 포인터 이거나, 태스크를 만들 수 없는 경우 null입니다. 작업은 [IHostTask:: Start](ihosttask-start-method.md)를 호출 하 여 명시적으로 시작 될 때까지 일시 중단 된 상태로 유지 됩니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`CreateTask` 성공적으로 반환 되었습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
|E_OUTOFMEMORY|메모리가 부족 하 여 요청한 작업을 만들 수 없습니다.|  
  
## <a name="remarks"></a>설명  

 CLR에서 `CreateTask` 를 호출 하 여 호스트가 새 작업을 만들도록 요청 합니다. 호스트는 인스턴스에 대 한 인터페이스 포인터를 반환 합니다 `IHostTask` . 반환 된 작업은에 대 한 호출에 의해 명시적으로 시작 될 때까지 일시 중단 된 상태로 유지 되어야 합니다 `IHostTask::Start` .  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRTask 인터페이스](iclrtask-interface.md)
- [ICLRTaskManager 인터페이스](iclrtaskmanager-interface.md)
- [IHostTask 인터페이스](ihosttask-interface.md)
- [IHostTaskManager 인터페이스](ihosttaskmanager-interface.md)
