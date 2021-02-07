---
description: '자세히 알아보기: IHostMemoryManager:: VirtualAlloc 메서드'
title: IHostMemoryManager::VirtualAlloc 메서드
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualAlloc
helpviewer_keywords:
- VirtualAlloc method [.NET Framework hosting]
- IHostMemoryManager::VirtualAlloc method [.NET Framework hosting]
ms.assetid: 4dff3646-a050-4bd9-ac31-fe307e8637ec
topic_type:
- apiref
ms.openlocfilehash: 28682aea5e6e7951b3b8f0a9af946a3f3828601b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707854"
---
# <a name="ihostmemorymanagervirtualalloc-method"></a>IHostMemoryManager::VirtualAlloc 메서드

해당 Win32 함수에 대 한 논리 래퍼로 사용 됩니다. 의 Win32 구현은 `VirtualAlloc` 호출 프로세스의 가상 주소 공간에서 페이지 영역을 예약 하거나 커밋합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT VirtualAlloc (  
    [in]  void*   pAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flAllocationType,  
    [in]  DWORD   flProtect,  
    [in]  EMemoryCriticalLevel dwCriticalLevel,  
    [out] void**  ppMem  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pAddress`  
 진행 할당할 영역의 시작 주소에 대 한 포인터입니다.  
  
 `dwSize`  
 진행 영역의 크기 (바이트)입니다.  
  
 `flAllocationType`  
 진행 메모리 할당의 유형입니다.  
  
 `flProtect`  
 진행 할당할 페이지 영역에 대 한 메모리 보호입니다.  
  
 `dwCriticalLevel`  
 진행 할당 오류의 영향을 나타내는 [EMemoryCriticalLevel](ememorycriticallevel-enumeration.md) 값입니다.  
  
 `ppMem`  
 제한이 할당 된 메모리의 시작 주소에 대 한 포인터 이거나, 요청을 충족 하지 못할 경우 null입니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`VirtualAlloc` 성공적으로 반환 되었습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
|E_OUTOFMEMORY|할당 요청을 완료 하는 데 사용할 수 있는 메모리가 부족 합니다.|  
  
## <a name="remarks"></a>설명  

 를 호출 하 여 프로세스의 주소 공간에서 영역을 예약 `VirtualAlloc` 합니다. `pAddress`매개 변수에는 원하는 메모리 블록의 시작 주소가 포함 됩니다. 이 매개 변수는 일반적으로 null로 설정 됩니다. 운영 체제는 프로세스에 사용할 수 있는 무료 주소 범위에 대 한 레코드를 유지 합니다. `pAddress`Null 값은 시스템이 적합 한 위치에 있는 영역을 예약 하도록 지시 합니다. 또는 메모리 블록에 대 한 특정 시작 주소를 제공할 수 있습니다. 두 경우 모두 출력 매개 변수는 `ppMem` 할당 된 메모리에 대 한 포인터로 반환 됩니다. 함수 자체는 HRESULT 값을 반환 합니다.  
  
 Win32 함수에는 `VirtualAlloc` `ppMem` 매개 변수가 없으며 대신 할당 된 메모리에 대 한 포인터를 반환 합니다. 자세한 내용은 Windows 플랫폼 설명서를 참조 하세요.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IHostMemoryManager 인터페이스](ihostmemorymanager-interface.md)
