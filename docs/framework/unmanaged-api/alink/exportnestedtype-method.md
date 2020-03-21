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
ms.openlocfilehash: 9ca2167e66ac3aa5bcc0e92ff357eed18d366c67
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179409"
---
# <a name="exportnestedtype-method"></a>ExportNestedType 메서드
중첩된 형식을 내보낼 수 있는 것으로 지정합니다. [ExportType 메서드는](exporttype-method.md) 중첩된 형식을 내보낼 수도 있지만 이 방법은 더 빠릅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
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
 내보낼 수 있도록 할 형식을 정의하는 파일 토큰 또는 파일 어셈블리입니다.  
  
 `TypeToken`  
 내보낼 수 있도록 할 형식의 토큰을 입력합니다.  
  
 `ParentType`  
 상위 형식의 토큰입니다.  
  
 `pszTypename`  
 내보낼 정규화된 형식 이름입니다.  
  
 `dwFlags`  
 `ComType`또는 와 `tdPublic` `tdNested`같은 플래그입니다. 이 값은 [정의ExportedType 메서드에](../metadata/imetadataassemblyemit-defineexportedtype-method.md)전달될 수 있습니다.  
  
 `pType`  
 내보낸 형식에 대한 토큰을 받습니다.  
  
## <a name="return-value"></a>Return Value  
 메서드가 성공하면 S_OK 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
 alink.h 필요  
  
## <a name="see-also"></a>참고 항목

- [IALink 인터페이스](ialink-interface.md)
- [IALink2 인터페이스](ialink2-interface.md)
- [ALink API](index.md)
