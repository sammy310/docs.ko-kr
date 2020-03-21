---
title: IHostMemoryManager::GetMemoryLoad 메서드
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.GetMemoryLoad
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::GetMemoryLoad
helpviewer_keywords:
- IHostMemoryManager::GetMemoryLoad method [.NET Framework hosting]
- GetMemoryLoad method [.NET Framework hosting]
ms.assetid: e8138f6e-a0a4-48d4-8dae-9466b4dc6180
topic_type:
- apiref
ms.openlocfilehash: 88acd50c83eb1ff4d59aa50d677db2383912659a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176281"
---
# <a name="ihostmemorymanagergetmemoryload-method"></a>IHostMemoryManager::GetMemoryLoad 메서드
호스트에서 보고한 대로 현재 사용 중인 실제 메모리의 양을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetMemoryLoad (  
    [out] DWORD*  pMemoryLoad,
    [out] SIZE_T  *pAvailableBytes  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pMemoryLoad`  
 【아웃】 현재 사용 중인 총 실제 메모리의 대략적인 백분율에 대한 포인터입니다.  
  
 `pAvailableBytes`  
 【아웃】 공통 언어 런타임(CLR)에서 사용할 수 있는 바이트 수에 대한 포인터입니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|`GetMemoryLoad`성공적으로 반환됩니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR이 프로세스에 로드되지 않았거나 CLR이 관리 코드를 실행하거나 호출을 성공적으로 처리할 수 없는 상태입니다.|  
|HOST_E_TIMEOUT|통화 시간이 시간 미정으로 확인되었습니다.|  
|HOST_E_NOT_OWNER|호출자는 잠금을 소유하지 않습니다.|  
|HOST_E_ABANDONED|차단된 스레드 또는 파이버가 대기하는 동안 이벤트가 취소되었습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생했습니다. 메서드가 E_FAIL 반환하면 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다. 호스팅 메서드에 대한 후속 호출은 HOST_E_CLRNOTAVAILABLE 반환합니다.|  
  
## <a name="remarks"></a>설명  
 `GetMemoryLoad`Win32 `GlobalMemoryStatus` 함수를 래핑합니다. `pMemoryLoad` 값은 에서 반환된 `dwMemoryLoad` 구조의 `MEMORYSTATUS` 필드와 `GlobalMemoryStatus`동일합니다.  
  
 런타임은 반환 값을 가비지 수집기의 추론값으로 사용합니다. 예를 들어 호스트가 대부분의 메모리가 사용 중이라고 보고하는 경우 가비지 수집기는 잠재적으로 사용 가능해질 수 있는 메모리 양을 늘리기 위해 여러 세대에서 수집하도록 선택할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MSCorE.h  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- <xref:System.GC?displayProperty=nameWithType>
- [IHostMemoryManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
