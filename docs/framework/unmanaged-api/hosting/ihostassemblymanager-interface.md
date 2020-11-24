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
ms.openlocfilehash: a06e7f13b6de9450aa2a81f28f591c0a3ce8db0f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680991"
---
# <a name="ihostassemblymanager-interface"></a>IHostAssemblyManager 인터페이스

호스트가 CLR (공용 언어 런타임) 또는 호스트에서 로드 해야 하는 어셈블리 집합을 지정 하는 데 사용할 수 있는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetAssemblyStore 메서드](ihostassemblymanager-getassemblystore-method.md)|호스트에서 로드 한 어셈블리 목록을 나타내는 [IHostAssemblyStore](ihostassemblystore-interface.md) 에 대 한 인터페이스 포인터를 가져옵니다.|  
|[GetNonHostStoreAssemblies 메서드](ihostassemblymanager-getnonhoststoreassemblies-method.md)|호스트에서 CLR을 로드 하는 데 필요한 어셈블리 목록을 나타내는 [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) 에 대 한 인터페이스 포인터를 가져옵니다.|  
  
## <a name="remarks"></a>설명  

 호스트는 또는를 구현할 필요가 없습니다 `IHostAssemblyManager` `IHostAssemblyStore` . 호스트에서를 구현 하는 경우 `IHostAssemblyManager` 도 구현 해야 `IHostAssemblyStore` 합니다.  
  
 런타임은 `IHostAssemblyManager` IID_IHostAssemblyManager의를 사용 하 여 초기화할 때 [IHostControl:: GetHostManager](ihostcontrol-gethostmanager-method.md) 를 호출 하 여에 대해 쿼리 합니다 `IID` .  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRAssemblyReferenceList 인터페이스](iclrassemblyreferencelist-interface.md)
- [IHostAssemblyStore 인터페이스](ihostassemblystore-interface.md)
- [IHostControl 인터페이스](ihostcontrol-interface.md)
- [호스팅 인터페이스](hosting-interfaces.md)
