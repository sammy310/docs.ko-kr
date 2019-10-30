---
title: IHostMalloc 인터페이스
ms.date: 03/30/2017
api_name:
- IHostMAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc
helpviewer_keywords:
- IHostMAlloc interface [.NET Framework hosting]
ms.assetid: e3c6643b-6fc7-4a99-959d-4b7b4e63fdee
topic_type:
- apiref
ms.openlocfilehash: abc6cca185b318be016f92ac8c97d21f7af5940a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136774"
---
# <a name="ihostmalloc-interface"></a>IHostMalloc 인터페이스
CLR (공용 언어 런타임)이 호스트를 통해 힙에서 세부적인 할당을 요청할 수 있는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Alloc 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md)|호스트에서 힙에서 요청 된 양의 메모리를 할당 하도록 요청 합니다.|  
|[DebugAlloc 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-debugalloc-method.md)|호스트가 힙에서 요청 된 메모리 양을 할당 하도록 요청 하 고 추가적으로 메모리가 할당 된 위치를 추적 하도록 요청 합니다.|  
|[Free 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-free-method.md)|`Alloc` 메서드를 사용 하 여 할당 된 메모리를 해제 합니다.|  
  
## <a name="remarks"></a>주의  
 CLR은 [IHostMemoryManager:: CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) 메서드를 호출 하 여 `IHostMalloc` 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [IHostMemoryManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
