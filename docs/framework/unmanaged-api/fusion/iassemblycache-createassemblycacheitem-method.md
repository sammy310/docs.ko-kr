---
description: '자세한 정보: IAssemblyCache:: CreateAssemblyCacheItem 메서드'
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
ms.openlocfilehash: 3377901d358bcf643ce0d30336c1c0cd8089e50c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760981"
---
# <a name="iassemblycachecreateassemblycacheitem-method"></a>IAssemblyCache::CreateAssemblyCacheItem 메서드

새 [Iassemblycacheitem](iassemblycacheitem-interface.md) 개체에 대 한 참조를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CreateAssemblyCacheItem (  
    [in]  DWORD dwFlags,  
    [in]  PVOID pvReserved,  
    [out] IAssemblyCacheItem **ppAsmItem,  
    [in, optional] LPCWSTR pszAssemblyName  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `dwFlags`  
 진행 Fusion에 정의 된 플래그입니다. 지원되는 값은 다음과 같습니다.  
  
- IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)  
  
- IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)  
  
 `pvReserved`  
 진행 향후 확장성을 위해 예약 되었습니다. `pvReserved` 는 null 참조 여야 합니다.  
  
 `ppAsmItem`  
 제한이 반환 된 `IAssemblyCacheItem` 포인터입니다.  
  
 `pszAssemblyName`  
 [in, 선택 사항] 정규화 되지 않은 쉼표로 구분 된 `name=value` 쌍입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Fusion. h  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IAssemblyCache 인터페이스](iassemblycache-interface.md)
- [IAssemblyCacheItem 인터페이스](iassemblycacheitem-interface.md)
