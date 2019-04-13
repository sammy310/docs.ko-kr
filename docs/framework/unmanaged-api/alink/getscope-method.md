---
title: GetScope 메서드
ms.date: 03/30/2017
api_name:
- IALink.GetScope
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetScope
helpviewer_keywords:
- GetScope method
ms.assetid: e1555328-2c71-4ece-b357-9eb6d3a8efc4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 571612796d4e66be9dd8469d748c2380c839ddfa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165788"
---
# <a name="getscope-method"></a>GetScope 메서드
가져오기 범위를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
## <a name="parameters"></a>매개 변수  
 `AssemblyID`  
 가져올 어셈블리의 고유 ID입니다.  
  
 `FileToken`  
 가져올 파일의 고유 ID입니다.  
  
 `dwScope`  
 가져오려는 0부터 시작 범위입니다.  
  
 `ppImportScope`  
 수신 [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) 범위에 대 한 인터페이스입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 Alink.h 필요  
  
## <a name="see-also"></a>참고자료

- [IALink 인터페이스](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [IALink2 인터페이스](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [ALink API](../../../../docs/framework/unmanaged-api/alink/index.md)
