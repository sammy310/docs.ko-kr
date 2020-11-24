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
ms.openlocfilehash: 4b2fed963d2d0ebec54e5f7a4d95cba26c1bac1f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680955"
---
# <a name="ihostassemblystore-interface"></a>IHostAssemblyStore 인터페이스

호스트가 CLR (공용 언어 런타임)과 독립적으로 어셈블리 및 모듈을 로드할 수 있도록 하는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[ProvideAssembly 메서드](ihostassemblystore-provideassembly-method.md)|[IHostAssemblyManager:: Getnonhost 어셈블리](ihostassemblymanager-getnonhoststoreassemblies-method.md)에 대 한 호출에서 반환 된 [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) 가 참조 하지 않는 어셈블리에 대 한 참조를 가져옵니다.|  
|[ProvideModule 메서드](ihostassemblystore-providemodule-method.md)|어셈블리 또는 연결 된 (포함 되지 않은) 리소스 파일 내에서 모듈을 확인 합니다.|  
  
## <a name="remarks"></a>설명  

 `IHostAssemblyStore` 호스트에서 어셈블리 id를 기반으로 어셈블리를 효율적으로 로드할 수 있는 방법을 제공 합니다. 호스트는 `IStream` 바이트를 직접 가리키는 인스턴스를 반환 하 여 어셈블리를 로드 합니다.  
  
 CLR은 `IHostAssemblyStore` 초기화 시를 호출 하 여 호스트가 구현 되었는지 여부를 확인 `IHostAssemblyManager::GetNonHostAssemblyStores` 합니다. 이를 통해 호스트는 사용자 어셈블리에 대 한 바인딩을 제어할 수 있을 뿐만 아니라 런타임에 의존 하 여 .NET Framework 어셈블리에 바인딩할 수 있습니다.  
  
> [!NOTE]
> 의 구현을 제공 하는 `IHostAssemblyStore` 경우 호스트는에서 반환 된에서 참조 하지 않는 모든 어셈블리를 확인 하는 용도를 지정 합니다 `ICLRAssemblyReferenceList` `IHostAssemblyManager::GetNonHostStoreAssemblies` .  
  
> [!NOTE]
> .NET Framework 버전 2.0는 호스트에서 [네이티브 이미지 생성기 (Ngen.exe)](../../tools/ngen-exe-native-image-generator.md) 유틸리티에 제공 된 어셈블리의 네이티브 이미지를 로드 하는 방법을 제공 하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRAssemblyReferenceList 인터페이스](iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager 인터페이스](ihostassemblymanager-interface.md)
- [호스팅 인터페이스](hosting-interfaces.md)
