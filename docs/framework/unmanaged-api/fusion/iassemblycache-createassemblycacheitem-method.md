---
title: IAssemblyCache::CreateAssemblyCacheItem 메서드
ms.date: 03/30/2017
api_name:
- IAssemblyCache.CreateAssemblyCacheItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::CreateAssemblyCacheItem
helpviewer_keywords:
- IAssemblyCache::CreateAssemblyCacheItem method [.NET Framework fusion]
- CreateAssemblyCacheItem method [.NET Framework fusion]
ms.assetid: 017a7ba5-aaaf-44e2-9cbe-ceebef259df0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 476f28b37efef483b31ad548d3db62c820d536c5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489061"
---
# <a name="iassemblycachecreateassemblycacheitem-method"></a>IAssemblyCache::CreateAssemblyCacheItem 메서드
새 참조를 가져옵니다 [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CreateAssemblyCacheItem (  
    [in]  DWORD dwFlags,  
    [in]  PVOID pvReserved,  
    [out] IAssemblyCacheItem **ppAsmItem,  
    [in, optional] LPCWSTR pszAssemblyName  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `dwFlags`  
 [in] 같은 값이 지원에 정의 된 플래그입니다. 다음 값이 지원 됩니다.  
  
-   IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)  
  
-   IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)  
  
 `pvReserved`  
 [in] 향후 확장성을 위해 예약 되어 있습니다. `pvReserved` null 참조 여야 합니다.  
  
 `ppAsmItem`  
 [out] 반환 된 `IAssemblyCacheItem` 포인터입니다.  
  
 `pszAssemblyName`  
 [in, 선택 사항] Uncanonicalized, 쉼표로 구분 된 `name=value` 쌍입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** Fusion.h  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료
- [IAssemblyCache 인터페이스](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
- [IAssemblyCacheItem 인터페이스](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
