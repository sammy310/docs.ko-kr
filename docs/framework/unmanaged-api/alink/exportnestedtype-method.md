---
title: ExportNestedType 메서드
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedType
- ExportNestedType
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedType
helpviewer_keywords:
- ExportNestedType method
ms.assetid: dec7df60-4d30-47c8-99db-72e0419e5f76
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ff159cf794d566be6478ef890c769a0ac72c9b25
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59176607"
---
# <a name="exportnestedtype-method"></a>ExportNestedType 메서드
내보낼 수 있도록 중첩 된 형식을 지정합니다. 합니다 [ExportType 메서드](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md) 내보내기 중첩 형식 수도 있지만이 메서드는 더 빠릅니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ExportNestedType(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    mdExportedType  ParentType,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;   
```  
  
## <a name="parameters"></a>매개 변수  
 `AssemblyID`  
 내보낼 어셈블리의 ID입니다.  
  
 `FileToken`  
 파일 토큰 또는 내보낼 수 있도록 지정할 형식을 정의 하는 파일의 어셈블리입니다.  
  
 `TypeToken`  
 내보낼 수 있도록 지정할 형식의 토큰을 입력 합니다.  
  
 `ParentType`  
 부모 형식의 토큰입니다.  
  
 `pszTypename`  
 내보낼 정규화 된 형식 이름입니다.  
  
 `dwFlags`  
 `ComType` 와 같은 플래그 `tdPublic` 또는 `tdNested`합니다. 이 값을 전달할 수 있습니다 [DefineExportedType 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)합니다.  
  
 `pType`  
 내보낸된 형식에 대 한 토큰을 받습니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 Alink.h 필요  
  
## <a name="see-also"></a>참고자료

- [IALink 인터페이스](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [IALink2 인터페이스](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [ALink API](../../../../docs/framework/unmanaged-api/alink/index.md)
