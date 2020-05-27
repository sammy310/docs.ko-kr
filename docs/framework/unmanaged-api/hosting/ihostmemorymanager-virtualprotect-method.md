---
title: IHostMemoryManager::VirtualProtect 메서드
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualProtect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualProtect
helpviewer_keywords:
- IHostMemoryManager::VirtualProtect method [.NET Framework hosting]
- VirtualProtect method [.NET Framework hosting]
ms.assetid: 13be0299-df0d-4951-aabf-0676a30b385f
topic_type:
- apiref
ms.openlocfilehash: 473a52b55f793abc76883b0a5cd5b2a04756d9f7
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804363"
---
# <a name="ihostmemorymanagervirtualprotect-method"></a>IHostMemoryManager::VirtualProtect 메서드
해당 Win32 함수에 대 한 논리 래퍼로 사용 됩니다. 의 Win32 구현은 `VirtualProtect` 호출 프로세스의 가상 주소 공간에서 커밋된 페이지 영역에 대 한 보호를 변경 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT VirtualProtect (  
    [in]  void*   lpAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flNewProtect,  
    [out] DWORD*  pflOldProtect  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `lpAddress`  
 진행 보호 특성을 변경할 가상 메모리의 기본 주소에 대 한 포인터입니다.  
  
 `dwSize`  
 진행 변경할 메모리 페이지 영역의 크기 (바이트)입니다.  
  
 `flNewProtect`  
 진행 적용할 메모리 보호의 유형입니다.  
  
 `pflOldProtect`  
 제한이 이전 메모리 보호 값에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|`VirtualProtect`성공적으로 반환 되었습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
  
## <a name="remarks"></a>설명  
 이 구현 `VirtualProtect` 에서는 HRESULT 값을 반환 하는 반면, Win32 구현은 성공 여부를 나타내는 0이 아닌 값을 반환 하 고 실패를 나타내는 0 값을 반환 합니다. 자세한 내용은 Windows 플랫폼 설명서를 참조 하세요.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IHostMemoryManager 인터페이스](ihostmemorymanager-interface.md)
