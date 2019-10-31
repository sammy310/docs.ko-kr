---
title: IHostMAlloc::Alloc 메서드
ms.date: 03/30/2017
api_name:
- IHostMAlloc.Alloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::Alloc
helpviewer_keywords:
- Alloc method, IHostMAlloc interface [.NET Framework hosting]
- IHostMAlloc::Alloc method [.NET Framework hosting]
ms.assetid: a3007f5e-d75d-4b37-842b-704e9edced5e
topic_type:
- apiref
ms.openlocfilehash: 9837e4e3428a0293c8e689b3f3e081aa07f055b2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192074"
---
# <a name="ihostmallocalloc-method"></a>IHostMAlloc::Alloc 메서드
호스트가 힙에서 지정 된 양의 메모리를 할당 하도록 요청 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Alloc (  
    [in] SIZE_T  cbSize,   
    [in] EMemoryCriticalLevel dwCriticalLevel,   
    [out] void** ppMem  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `cbSize`  
 진행 현재 메모리 할당 요청의 크기 (바이트)입니다.  
  
 `dwCriticalLevel`  
 진행 할당 오류의 영향을 나타내는 [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) 값 중 하나입니다.  
  
 `ppMem`  
 제한이 할당 된 메모리에 대 한 포인터 이거나, 요청을 완료할 수 없는 경우 null입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`Alloc` 성공적으로 반환 되었습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다. 호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.|  
|E_OUTOFMEMORY|할당 요청을 완료 하는 데 사용할 수 있는 메모리가 부족 합니다.|  
  
## <a name="remarks"></a>주의  
 CLR은 [IHostMemoryManager:: CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) 메서드를 호출 하 여 `IHostMalloc` 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [IHostMemoryManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [IHostMalloc 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
