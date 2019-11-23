---
title: GetScope2 메서드
ms.date: 03/30/2017
api_name:
- IALink2.GetScope2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetScope2
helpviewer_keywords:
- GetScope2 method
ms.assetid: 49435665-6f5a-4acd-9034-8c9244a04a63
topic_type:
- apiref
ms.openlocfilehash: a5b080443be94d5a298cc67591914d87470e6f48
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447190"
---
# <a name="getscope2-method"></a>GetScope2 메서드
Gets an import scope.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetScope2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport2** ppImportScope  
) PURE;   
```  
  
## <a name="parameters"></a>매개 변수  
 `AssemblyID`  
 ID of target assembly.  
  
 `FileToken`  
 ID of file from which to import.  
  
 `dwScope`  
 Zero-based scope to import.  
  
 `ppImportScope`  
 Receives pointer to [IMetaDataImport2 Interface](../metadata/imetadataimport2-interface.md) interface for indicated scope.  
  
## <a name="return-value"></a>반환 값  
 Returns S_OK if the method succeeds.  
  
## <a name="requirements"></a>요구 사항  
 Requires alink.h.  
  
## <a name="see-also"></a>참조

- [IALink2 인터페이스](ialink2-interface.md)
- [IALink 인터페이스](ialink-interface.md)
- [ALink API](index.md)
