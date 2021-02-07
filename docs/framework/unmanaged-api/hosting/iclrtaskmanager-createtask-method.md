---
description: '자세히 알아보기: ICLRTaskManager:: CreateTask 메서드'
title: ICLRTaskManager::CreateTask 메서드
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.CreateTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::CreateTask
helpviewer_keywords:
- ICLRTaskManager::CreateTask method [.NET Framework hosting]
- CreateTask method, ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: eea570d9-2e53-4320-9ea0-eb777bf9dcf3
topic_type:
- apiref
ms.openlocfilehash: 98a287f10a84b18579ebf2a4294cbb8a67cabc9c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728615"
---
# <a name="iclrtaskmanagercreatetask-method"></a>ICLRTaskManager::CreateTask 메서드

CLR (공용 언어 런타임)이 새 작업을 만들도록 명시적으로 요청 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CreateTask (  
    [out] ICLRTask **pTask  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pTask`  
 제한이 새로 만든 [ICLRTask](iclrtask-interface.md)의 주소에 대 한 포인터 이거나, 태스크를 만들 수 없는 경우 null입니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|메서드가 성공적으로 반환했습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
|E_OUTOFMEMORY|메모리가 부족 하 여 요청 된 리소스를 할당할 수 없습니다.|  
  
## <a name="remarks"></a>설명  

 사용자 코드에서 네임 스페이스의 형식을 사용 하 여 스레드를 만들거나 <xref:System.Threading> 스레드 풀의 크기가 증가할 때 CLR은 초기화 시 자동으로 새 작업을 만듭니다. 또한 비관리 코드에서 관리 되는 함수를 호출할 때 작업을 만듭니다.  
  
 `CreateTask` 호스트가 CLR에서 새 작업을 만들도록 명시적 요청을 수행할 수 있습니다. 예를 들어 호스트는이 메서드를 호출 하 여 데이터 구조를 미리 초기화할 수 있습니다.  
  
> [!IMPORTANT]
> 새 작업은 일시 중단 된 상태로 반환 되 고 호스트가 명시적으로 [IHostTask:: Start](ihosttask-start-method.md)를 호출할 때까지 일시 중단 된 상태로 유지 됩니다.  
  
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
