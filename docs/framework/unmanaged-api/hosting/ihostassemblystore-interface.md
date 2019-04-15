---
title: IHostAssemblyStore 인터페이스
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore
helpviewer_keywords:
- IHostAssemblyStore interface [.NET Framework hosting]
ms.assetid: cccb650f-abe0-41e2-9fd1-b383788eb1f6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d4067c1fbcf99c903c892eaec58262d95569114b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59173422"
---
# <a name="ihostassemblystore-interface"></a>IHostAssemblyStore 인터페이스
호스트 어셈블리와는 CLR (공용 언어 런타임)와 독립적으로 모듈을 로드 하는 데 사용할 수 있는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[ProvideAssembly 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)|참조 되지 않은 어셈블리에 대 한 참조를 가져옵니다 합니다 [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) 에 대 한 호출에서 반환 된 [ihostassemblymanager:: Getnonhoststoreassemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)합니다.|  
|[ProvideModule 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)|어셈블리 또는 연결된 (포함된 되지 않은) 리소스 파일 내에서 모듈을 확인합니다.|  
  
## <a name="remarks"></a>설명  
 `IHostAssemblyStore` 어셈블리 id에 따라 효율적으로 어셈블리를 로드 하는 호스트에 대 한 방법을 제공 합니다. 반환 하 여 어셈블리를 로드 하는 호스트 `IStream` 직접적으로 바이트를 가리키는 인스턴스.  
  
 CLR 호스트에 구현 여부를 결정 `IHostAssemblyStore` 를 호출 하 여 `IHostAssemblyManager::GetNonHostAssemblyStores` 를 초기화 합니다. 이렇게 하면 호스트, 예를 들어, 사용자 어셈블리 바인딩을 제어할 수 있지만 런타임에서.NET Framework 어셈블리에 바인딩할 수 있습니다.  
  
> [!NOTE]
>  구현을 제공 `IHostAssemblyStore`, 호스트에서 참조 되지 않은 모든 어셈블리를 확인 하도록 지정 합니다 `ICLRAssemblyReferenceList` 에서 반환 된 `IHostAssemblyManager::GetNonHostStoreAssemblies`합니다.  
  
> [!NOTE]
>  제공 된 대로.NET Framework 버전 2.0 호스트가 어셈블리의 네이티브 이미지를 로드 하는 데 사용할 방법을 제공 하지 않습니다 합니다 [네이티브 이미지 생성기 (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) 유틸리티입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [ICLRAssemblyReferenceList 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
