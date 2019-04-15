---
title: IHostMemoryManager::VirtualQuery 메서드
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualQuery
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualQuery
helpviewer_keywords:
- IHostMemoryManager::VirtualQuery method [.NET Framework hosting]
- VirtualQuery method [.NET Framework hosting]
ms.assetid: 757af1e6-b9e8-49e7-b5db-342be3aa205f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 028ca0b9cb917d3e6cc0242cbc8c3f4a5a19ab39
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199624"
---
# <a name="ihostmemorymanagervirtualquery-method"></a>IHostMemoryManager::VirtualQuery 메서드
역할을 해당 하는 Win32 함수에 대 한 논리적 래퍼입니다. Win32 구현의 `VirtualQuery` 호출 프로세스의 가상 주소 공간에서 페이지 범위에 대 한 정보를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT VirtualQuery (  
    [in]  void*    lpAddress,  
    [out] void*    lpBuffer,  
    [in]  SIZE_T   dwLength,  
    [out] SIZE_T*  pResult  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `lpAddress`  
 [in] 쿼리할 수 있는 가상 메모리 주소에 대 한 포인터입니다.  
  
 `lpBuffer`  
 [out] 지정 된 메모리 영역에 대 한 정보를 포함 하는 구조체에 대 한 포인터입니다.  
  
 `dwLength`  
 [in] 버퍼의 바이트 크기는 `lpBuffer` 가리킵니다.  
  
 `pResult`  
 [out] 정보 버퍼에서 반환 된 바이트 수에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`VirtualQuery` 성공적으로 반환 합니다.|  
|HOST_E_CLRNOTAVAILABLE|프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다. 메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.|  
  
## <a name="remarks"></a>설명  
 `VirtualQuery` 호출 프로세스의 가상 주소 공간에서 페이지 범위에 대 한 정보를 제공합니다. 값을 설정 하는이 구현 된 `pResult` 바이트 수에 대 한 매개 변수 정보 버퍼에 반환 하 고 HRESULT 값을 반환 합니다. Win32에서 `VirtualQuery` 함수 반환 값은 버퍼 크기입니다. 자세한 내용은 Windows 플랫폼 설명서를 참조 하십시오.  
  
> [!IMPORTANT]
>  운영 체제의 구현의 `VirtualQuery` 교착 상태가 발생 하지 않습니다 및 사용자 코드에서 일시 중단 하는 임의 스레드를 사용 하 여 실행을 완료할 수 있습니다. 이 메서드의 호스팅되는 버전을 구현 하는 경우에 주의 기울여야를 사용 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [IHostMemoryManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
