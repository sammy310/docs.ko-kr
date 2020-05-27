---
title: IHostTask::Start 메서드
ms.date: 03/30/2017
api_name:
- IHostTask.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Start
helpviewer_keywords:
- IHostTask::Start method [.NET Framework hosting]
- Start method, IHostTask interface [.NET Framework hosting]
ms.assetid: b18742b0-d8c4-401c-ae89-e6eccdaa81d0
topic_type:
- apiref
ms.openlocfilehash: a4e8211f091b2a3a4f24d8350f6d7dbe7d7920af
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842389"
---
# <a name="ihosttaskstart-method"></a>IHostTask::Start 메서드
호스트가 현재 [IHostTask](ihosttask-interface.md) 인스턴스로 표시 된 작업을 일시 중단에서 라이브 상태로 이동 하 여 코드를 실행할 수 있도록 요청 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Start ();  
```  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|시작이 성공적으로 반환 되었습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 하는 경우 프로세스 내에서 CLR (공용 언어 런타임)을 더 이상 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
  
## <a name="remarks"></a>설명  
 `Start`는 치명적인 오류가 발생 한 경우를 제외 하 고는 항상 S_OK HRESULT 값을 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRTask 인터페이스](iclrtask-interface.md)
- [ICLRTaskManager 인터페이스](iclrtaskmanager-interface.md)
- [IHostTask 인터페이스](ihosttask-interface.md)
- [IHostTaskManager 인터페이스](ihosttaskmanager-interface.md)
