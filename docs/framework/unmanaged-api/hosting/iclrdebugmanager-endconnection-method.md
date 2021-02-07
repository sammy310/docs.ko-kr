---
description: '자세히 알아보기: ICLRDebugManager:: EndConnection 메서드'
title: ICLRDebugManager::EndConnection 메서드
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.EndConnection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::EndConnection
helpviewer_keywords:
- ICLRDebugManager::EndConnection method [.NET Framework hosting]
- EndConnection method [.NET Framework hosting]
ms.assetid: 89dc7363-2f29-4eb2-8f23-fccdda6a76a6
topic_type:
- apiref
ms.openlocfilehash: 06dc9e20ec02c3e3040090babcc443a2ae59848b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746054"
---
# <a name="iclrdebugmanagerendconnection-method"></a>ICLRDebugManager::EndConnection 메서드

작업 목록과 식별자 및 이름 간의 연결을 제거 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EndConnection (  
    [in] CONNID dwConnectionId  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `dwConnectionId`  
 진행 연결에 대 한 호스트 관련 식별자와 관련 된 CLR (공용 언어 런타임) 작업 목록입니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`EndConnection` 성공적으로 반환 되었습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
|E_INVALIDARG|[Beginconnection](iclrdebugmanager-beginconnection-method.md) 이를 사용 하 여 호출 되지 `dwConnectionId` 않았거나 `dwConnectionId` 가 0입니다.|  
  
## <a name="remarks"></a>설명  

 [ICLRDebugManager](iclrdebugmanager-interface.md) 는 작업 목록과 식별자를 연결 하는 데 사용 되는 세 가지 메서드인, `BeginConnection` [setconnectiontasks](iclrdebugmanager-setconnectiontasks-method.md)및 `EndConnection` 를 제공 합니다.  
  
> [!IMPORTANT]
> 이러한 세 메서드는 각 작업 집합에 대해 특정 순서로 호출 되어야 합니다. `BeginConnection` 새 연결을 설정 하기 위해가 먼저 호출 됩니다. `SetConnectionTasks` 는 해당 연결과 관련 된 태스크 집합을 제공 하기 위해 다음에 호출 됩니다. `EndConnection` 작업 목록과 식별자와 이름 간의 연결을 제거 하기 위해 마지막으로 호출 됩니다. 그러나 다른 연결에 대 한 호출은 중첩할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRControl 인터페이스](iclrcontrol-interface.md)
- [ICLRDebugManager 인터페이스](iclrdebugmanager-interface.md)
- [BeginConnection 메서드](iclrdebugmanager-beginconnection-method.md)
- [SetConnectionTasks 메서드](iclrdebugmanager-setconnectiontasks-method.md)
- [IHostControl 인터페이스](ihostcontrol-interface.md)
