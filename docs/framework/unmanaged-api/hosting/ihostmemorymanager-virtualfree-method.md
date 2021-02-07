---
description: '자세히 알아보기: IHostMemoryManager:: VirtualFree 메서드'
title: IHostMemoryManager::VirtualFree 메서드
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualFree
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualFree
helpviewer_keywords:
- IHostMemoryManager::VirtualFree method [.NET Framework hosting]
- VirtualFree method [.NET Framework hosting]
ms.assetid: 1a436e89-eb28-4d15-bcf1-a072f86dbd99
topic_type:
- apiref
ms.openlocfilehash: 987661ce1b7bfd08f757f53082313b8eb60ff282
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707540"
---
# <a name="ihostmemorymanagervirtualfree-method"></a>IHostMemoryManager::VirtualFree 메서드

해당 Win32 함수에 대 한 논리 래퍼로 사용 됩니다. 의 Win32 구현은 호출 하는 `VirtualFree` 프로세스의 가상 주소 공간 내에서 페이지 영역을 해제, 커밋 취소 또는 해제 하 고 커밋을 취소 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT VirtualFree (  
    [in] LPVOID  lpAddress,  
    [in] SIZE_T  dwSize,  
    [in] DWORD   dwFreeType  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `lpAddress`  
 진행 해제할 가상 메모리 페이지의 기본 주소에 대 한 포인터입니다.  
  
 `dwSize`  
 진행 해제할 영역의 크기 (바이트)입니다.  
  
 `dwFreeType`  
 진행 해제 작업의 유형입니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`VirtualFree` 성공적으로 반환 되었습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
|HOST_E_INVALIDOPERATION|호스트를 통해 할당 되지 않은 메모리를 해제 하려고 했습니다.|  
  
## <a name="remarks"></a>설명  

 `VirtualFree``lpAddress` [IHostMemoryManager:: VirtualAlloc](ihostmemorymanager-virtualalloc-method.md) 함수에 대 한 이전 호출을 통해 매개 변수와 연결 된 가상 메모리 페이지를 해제 합니다. 호스트를 통해 할당 되지 않은 메모리를 해제 하려는 시도는 HOST_E_INVALIDOPERATION을 반환 해야 합니다.  
  
 의미 체계는의 Win32 구현에 대 한 의미 체계와 동일 합니다 `VirtualFree` . 자세한 내용은 Windows 플랫폼 설명서를 참조 하세요.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IHostMemoryManager 인터페이스](ihostmemorymanager-interface.md)
- [IHostMalloc 인터페이스](ihostmalloc-interface.md)
