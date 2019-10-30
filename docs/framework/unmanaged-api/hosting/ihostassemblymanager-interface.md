---
title: IHostAssemblyManager 인터페이스
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager
helpviewer_keywords:
- IHostAssemblyManager interface [.NET Framework hosting]
ms.assetid: dfec05bb-3cd7-4bd5-b396-a4f097c3a636
topic_type:
- apiref
ms.openlocfilehash: d9feeaf5f85d6f84a13e74a893b82c97fdaf023c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124517"
---
# <a name="ihostassemblymanager-interface"></a>IHostAssemblyManager 인터페이스
호스트가 CLR (공용 언어 런타임) 또는 호스트에서 로드 해야 하는 어셈블리 집합을 지정 하는 데 사용할 수 있는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetAssemblyStore 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getassemblystore-method.md)|호스트에서 로드 한 어셈블리 목록을 나타내는 [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) 에 대 한 인터페이스 포인터를 가져옵니다.|  
|[GetNonHostStoreAssemblies 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)|호스트에서 CLR을 로드 하는 데 필요한 어셈블리 목록을 나타내는 [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) 에 대 한 인터페이스 포인터를 가져옵니다.|  
  
## <a name="remarks"></a>주의  
 호스트는 `IHostAssemblyManager` 또는 `IHostAssemblyStore`를 구현 하는 데 필요 하지 않습니다. 호스트에서 `IHostAssemblyManager`를 구현 하는 경우 `IHostAssemblyStore`도 구현 해야 합니다.  
  
 런타임은 IID_IHostAssemblyManager의 `IID`를 사용 하 여 초기화할 때 [IHostControl:: GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) 를 호출 하 여 `IHostAssemblyManager`를 쿼리 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRAssemblyReferenceList 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [IHostAssemblyStore 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [IHostControl 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
- [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
