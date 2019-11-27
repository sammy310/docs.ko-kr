---
title: ExportNestedTypeForwarder 메서드
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedTypeForwarder
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedTypeForwarder
helpviewer_keywords:
- ExportNestedTypeForwarder method
ms.assetid: 886ea6c5-6b26-4b88-8bf6-448d6d191950
topic_type:
- apiref
ms.openlocfilehash: cc81ccd1c754e3d34c54737f4560b4f81d5cc916
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438419"
---
# <a name="exportnestedtypeforwarder-method"></a>ExportNestedTypeForwarder 메서드
중첩 된 형식의 형식 전달자를 지정 된 어셈블리의 형식 테이블에 추가 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ExportNestedTypeForwarder(  
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
 형식을 정의 하는 파일의 파일 토큰 또는 어셈블리 ID입니다.  
  
 `TypeToken`  
 형식에 대 한 토큰입니다.  
  
 `ParentType`  
 부모 형식의 토큰입니다.  
  
 `pszTypename`  
 내보낼 정규화 된 형식 이름입니다.  
  
 `dwFlags`  
 `tdPublic` 또는 `tdNested`와 같은 플래그를 `ComType` 합니다.  
  
 `pType`  
 내보내기 유형의 토큰을 받습니다. 중첩 된 형식을 내보내는 경우에만 필요 합니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK을 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 Alink 필요  
  
## <a name="see-also"></a>참고자료

- [IALink 인터페이스](ialink-interface.md)
- [IALink2 인터페이스](ialink2-interface.md)
- [ALink API](index.md)
