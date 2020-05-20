---
title: ICLRIoCompletionManager::OnComplete 메서드
ms.date: 03/30/2017
api_name:
- ICLRIoCompletionManager.OnComplete
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRIoCompletionManager::OnComplete
helpviewer_keywords:
- OnComplete method [.NET Framework hosting]
- ICLRIoCompletionManager::OnComplete method [.NET Framework hosting]
ms.assetid: 003f6974-9727-4322-bed5-e330d1224d0b
topic_type:
- apiref
ms.openlocfilehash: 39c9752912e88b04455516c0e9bed43610ba8aa0
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703818"
---
# <a name="iclriocompletionmanageroncomplete-method"></a>ICLRIoCompletionManager::OnComplete 메서드
[IHostIoCompletionManager:: Bind](ihostiocompletionmanager-bind-method.md) 메서드를 호출 하 여 수행 된 i/o 요청의 상태를 CLR (공용 언어 런타임)에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT OnComplete (  
    [in] DWORD dwErrorCode,  
    [in] DWORD NumberOfBytesTransferred,  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `dwErrorCode`  
 진행 바인딩 작업의 상태를 나타내는 HRESULT 값입니다.  
  
- S_OK 작업이 성공적으로 완료 되었음을 나타냅니다.  
  
- HOST_E_INTERRUPTED는 호출이 완료 되기 전에 종료 되었음을 나타냅니다.  
  
- E_FAIL은 알 수 없거나 복구할 수 없는 치명적인 오류가 발생 했음을 나타냅니다.  
  
 `NumberOfBytesTransferred`  
 진행 I/o 요청을 처리 하는 동안 전송 된 바이트 수입니다.  
  
 `pvOverlapped`  
 진행 `OVERLAPPED`메서드 호출에 전달 된 구조체에 대 한 포인터 `IHostIoCompletionManager::Bind` 입니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`OnComplete`성공적으로 반환 되었습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
  
## <a name="remarks"></a>설명  
 호스트에서 i/o 완료 추상화를 구현 하는 경우 CLR은 [IHostIoCompletionManager](ihostiocompletionmanager-interface.md)의 메서드를 사용 하 여 호스트를 통해 i/o 요청을 만듭니다. 그런 다음 호스트는 메서드를 호출 `OnComplete` 하 여 이러한 요청의 결과를 런타임에 알립니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRIoCompletionManager 인터페이스](iclriocompletionmanager-interface.md)
- [IHostIoCompletionManager 인터페이스](ihostiocompletionmanager-interface.md)
- [IHostThreadPoolManager 인터페이스](ihostthreadpoolmanager-interface.md)
