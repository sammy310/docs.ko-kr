---
title: IHostMAlloc::DebugAlloc 메서드
ms.date: 03/30/2017
api_name:
- IHostMAlloc.DebugAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::DebugAlloc
helpviewer_keywords:
- DebugAlloc method [.NET Framework hosting]
- IHostMAlloc::DebugAlloc method [.NET Framework hosting]
ms.assetid: 0bfbc527-bea2-43ce-b041-69186f4440dd
topic_type:
- apiref
ms.openlocfilehash: 20ad5485b8603cc7de1c27c00d53c8939871d525
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178032"
---
# <a name="ihostmallocdebugalloc-method"></a>IHostMAlloc::DebugAlloc 메서드
호스트가 힙에서 지정된 양의 메모리를 할당하고 메모리가 할당된 위치를 추가로 추적할 것을 요청합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DebugAlloc (  
    [in]  SIZE_T  cbSize,
    [in]  EMemoryCriticalLevel dwCriticalLevel,
    [in]  char*   pszFileName,
    [in]  int     iLineNo,
    [out] void**  ppMem  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `cbSize`  
 【인】 현재 메모리 할당 요청의 크기(바이트)입니다.  
  
 `dwCriticalLevel`  
 【인】 할당 실패의 영향을 나타내는 [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) 값 중 하나입니다.  
  
 `pszFileName`  
 【인】 디버깅 중인 실행 파일의 코드 파일입니다.  
  
 `iLineNo`  
 【인】 할당이 `pszFileName` 요청된 줄 번호입니다.  
  
 `ppMem`  
 【아웃】 할당된 메모리에 대한 포인터 또는 요청을 완료할 수 없는 경우 null입니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|`DebugAlloc`성공적으로 반환됩니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR이 프로세스에 로드되지 않았거나 CLR이 관리 코드를 실행하거나 호출을 성공적으로 처리할 수 없는 상태입니다.|  
|HOST_E_TIMEOUT|통화 시간이 시간 미정으로 확인되었습니다.|  
|HOST_E_NOT_OWNER|호출자는 잠금을 소유하지 않습니다.|  
|HOST_E_ABANDONED|차단된 스레드 또는 파이버가 대기하는 동안 이벤트가 취소되었습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생했습니다. 메서드가 E_FAIL 반환하면 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다. 호스팅 메서드에 대한 후속 호출은 HOST_E_CLRNOTAVAILABLE 반환합니다.|  
|E_OUTOFMEMORY|할당 요청을 완료하는 데 사용할 수 있는 메모리가 부족합니다.|  
  
## <a name="remarks"></a>설명  
 CLR은 [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) 메서드를 호출하여 [IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) 인스턴스에 대한 인터페이스 포인터를 가져옵니다. `DebugAlloc`런타임에서 디버깅 중에 사용할 코드 파일 정보를 얻을 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MSCorE.h  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IHostMemoryManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [IHostMalloc 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
