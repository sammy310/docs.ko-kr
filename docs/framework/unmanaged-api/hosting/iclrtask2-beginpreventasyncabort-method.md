---
description: '자세히 알아보기: ICLRTask2:: BeginPreventAsyncAbort 메서드'
title: ICLRTask2::BeginPreventAsyncAbort 메서드
ms.date: 03/30/2017
api_name:
- ICLRTask2.BeginPreventAsyncAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2::BeginPreventAsyncAbort
helpviewer_keywords:
- ICLRTask2::BeginPreventAsyncAbort method [.NET Framework hosting]
- BeginPreventAsyncAbort method [.NET Framework hosting]
ms.assetid: 75754c2f-38c7-4707-85fe-559db4542729
topic_type:
- apiref
ms.openlocfilehash: 1e25cb0e6157d77efc6a04016dc49d9d5d0bf116
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728638"
---
# <a name="iclrtask2beginpreventasyncabort-method"></a>ICLRTask2::BeginPreventAsyncAbort 메서드

현재 스레드에 대 한 스레드 중단으로 인해 발생 하는 새 스레드 중단 요청을 지연 시킵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT BeginPreventAsyncAbort();  
```  
  
## <a name="return-value"></a>Return Value  

 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|HOST_E_INVALIDOPERATION|현재 스레드가 아닌 스레드에서 메서드가 호출 된 경우|  
  
## <a name="remarks"></a>설명  

 이 메서드를 호출 하면 현재 스레드에 대 한 지연 스레드 중단 카운터가 1 씩 증가 합니다.  
  
 `BeginPreventAsyncAbort`및 [ICLRTask2:: EndPreventAsyncAbort](iclrtask2-endpreventasyncabort-method.md) 에 대 한 호출은 중첩할 수 있습니다. 카운터가 0 보다 큰 경우 현재 스레드에 대 한 스레드 중단이 지연 됩니다. 이 호출이 메서드 호출과 쌍을 이루지 않으면 `EndPreventAsyncAbort` 스레드 중단을 현재 스레드에 전달할 수 없는 상태에 도달할 수 있습니다.  
  
 자체를 중단 하는 스레드에는 지연이 적용 되지 않습니다.  
  
 이 기능에 의해 노출 되는 기능은 VM (가상 컴퓨터)에서 내부적으로 사용 됩니다. 이러한 메서드를 잘못 지정 하면 VM에서 지정 되지 않은 동작이 발생할 수 있습니다. 예를 들어를 `EndPreventAsyncAbort` 먼저 호출 하지 않고를 호출 하면 `BeginPreventAsyncAbort` VM이 이전에 증가 한 경우 카운터를 0으로 설정할 수 있습니다. 마찬가지로 내부 카운터는 오버플로를 검사 하지 않습니다. 호스트와 VM이 모두 증가 하 여 정수 한도를 초과 하는 경우 결과 동작은 지정 되지 않습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [EndPreventAsyncAbort 메서드](iclrtask2-endpreventasyncabort-method.md)
- [ICLRTask2 인터페이스](iclrtask2-interface.md)
- [ICLRTaskManager 인터페이스](iclrtaskmanager-interface.md)
- [IHostTask 인터페이스](ihosttask-interface.md)
- [IHostTaskManager 인터페이스](ihosttaskmanager-interface.md)
- [호스팅 인터페이스](hosting-interfaces.md)
