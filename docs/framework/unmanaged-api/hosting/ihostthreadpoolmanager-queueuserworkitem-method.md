---
title: IHostThreadPoolManager::QueueUserWorkItem 메서드
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.QueueUserWorkItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::QueueUserWorkItem
helpviewer_keywords:
- IHostThreadPoolManager::QueueUserWorkItem method [.NET Framework hosting]
- QueueUserWorkItem method [.NET Framework hosting]
ms.assetid: 41602053-8670-4827-9d61-cbfcba509b9c
topic_type:
- apiref
ms.openlocfilehash: b3d77e30cd48310c392d38dc29f62fab565c8b42
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842467"
---
# <a name="ihostthreadpoolmanagerqueueuserworkitem-method"></a>IHostThreadPoolManager::QueueUserWorkItem 메서드
실행을 위해 함수를 큐에 대기 시키고 해당 함수에서 사용할 데이터가 포함 된 개체를 지정 합니다. 이 함수는 스레드를 사용할 수 있을 때 실행 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT QueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID Context,  
    [in] ULONG Flags  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `Function`  
 진행 실행할 함수를 나타내는 함수 포인터입니다.  
  
 `Context`  
 진행 에서 사용할 데이터를 포함 하는 개체입니다 `Function` .  
  
 `Flags`  
 진행 Win32 메서드에 대해 정의 된 대로 `QueueUserWorkItem` 실행을 제어 하는 플래그 값 중 하나입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|`QueueUserWorkItem`성공적으로 반환 되었습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
  
## <a name="remarks"></a>설명  
 `QueueUserWorkItem`스레드 풀의 작업자 스레드에 작업 항목을 큐에 대기 시킵니다. 해당 시그니처와 매개 변수 형식은 동일한 이름을 가진 해당 Win32 함수의 이름과 동일 합니다. 자세한 내용은 Windows 플랫폼 설명서를 참조 하세요.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>
- <xref:System.Threading.ThreadPool>
- [IHostThreadPoolManager 인터페이스](ihostthreadpoolmanager-interface.md)
