---
title: IHostMemoryManager 인터페이스
ms.date: 03/30/2017
api_name:
- IHostMemoryManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager
helpviewer_keywords:
- IHostMemoryManager interface [.NET Framework hosting]
ms.assetid: a945d439-3b34-4aa4-b575-8413dd7806ce
topic_type:
- apiref
ms.openlocfilehash: 4e7e76a4a3ab291ee97ad0912e3d6224cdf96fba
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804495"
---
# <a name="ihostmemorymanager-interface"></a>IHostMemoryManager 인터페이스
표준 Win32 가상 메모리 함수를 사용 하는 대신 CLR (공용 언어 런타임)에서 호스트를 통해 가상 메모리 요청을 수행할 수 있도록 하는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|Description|  
|------------|-----------------|  
|[AcquiredVirtualAddressSpace 메서드](ihostmemorymanager-acquiredvirtualaddressspace-method.md)|CLR (공용 언어 런타임)이 운영 체제에서 지정 된 메모리를 획득 했음을 호스트에 알립니다.|  
|[CreateMAlloc 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)|호스트에서 만든 힙에서 메모리 할당을 요청 하는 데 사용 되는 [IHostMAlloc](ihostmalloc-interface.md) 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.|  
|[GetMemoryLoad 메서드](ihostmemorymanager-getmemoryload-method.md)|호스트에서 보고 하는 현재 사용 중인 실제 메모리의 양을 가져옵니다.|  
|[NeedsVirtualAddressSpace 메서드](ihostmemorymanager-needsvirtualaddressspace-method.md)|CLR에서 지정 된 메모리를 사용 하려고 함을 호스트에 알립니다.|  
|[RegisterMemoryNotificationCallback 메서드](ihostmemorymanager-registermemorynotificationcallback-method.md)|호스트에서 컴퓨터의 현재 메모리 로드를 알리기 위해 호출 하는 콜백 함수에 대 한 포인터를 등록 합니다.|  
|[ReleasedVirtualAddressSpace 메서드](ihostmemorymanager-releasedvirtualaddressspace-method.md)|지정 된 메모리를 사용 하 여 CLR이 완료 되었음을 호스트에 알립니다.|  
|[VirtualAlloc 메서드](ihostmemorymanager-virtualalloc-method.md)|호출 프로세스의 가상 주소 공간에서 페이지 영역을 예약 하거나 커밋하는 해당 Win32 함수에 대 한 논리 래퍼로 사용 됩니다.|  
|[VirtualFree 메서드](ihostmemorymanager-virtualfree-method.md)|호출 프로세스의 가상 주소 공간 내에서 페이지 영역을 릴리스, 커밋 취소 또는 해제 하 고 커밋을 취소 하는 해당 Win32 함수에 대 한 논리 래퍼로 사용 됩니다.|  
|[VirtualProtect 메서드](ihostmemorymanager-virtualprotect-method.md)|호출 프로세스의 가상 주소 공간에서 커밋된 페이지 영역에 대 한 보호를 변경 하는 해당 Win32 함수에 대 한 논리 래퍼로 사용 됩니다.|  
|[VirtualQuery 메서드](ihostmemorymanager-virtualquery-method.md)|호출 프로세스의 가상 주소 공간에 있는 페이지 범위에 대 한 정보를 검색 하는 해당 Win32 함수에 대 한 논리 래퍼로 사용 됩니다.|  
  
## <a name="remarks"></a>설명  
 `IHostMemoryManager`는 또한 CLR에서 힙에 대 한 메모리 요청을 수행 하 고 호스트에서 보고 하는 프로세스의 메모리 압력 수준을 가져오는 포인터를 가져오는 메서드를 제공 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IHostMalloc 인터페이스](ihostmalloc-interface.md)
- [호스팅 인터페이스](hosting-interfaces.md)
