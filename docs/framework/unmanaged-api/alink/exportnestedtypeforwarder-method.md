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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 050ed0bbd4da38bede5a56ff95d0243f5f3cf1da
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789911"
---
# <a name="exportnestedtypeforwarder-method"></a>ExportNestedTypeForwarder 메서드
중첩 된 형식에 대 한 형식 전달 자가 지정된 된 어셈블리의 type 테이블에 추가합니다.  
  
## <a name="syntax"></a>구문  
  
```  
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
 내보내는 어셈블리의 ID입니다.  
  
 `FileToken`  
 파일 형식을 정의 하는 파일의 토큰 또는 어셈블리 ID입니다.  
  
 `TypeToken`  
 토큰 형식입니다.  
  
 `ParentType`  
 부모 형식의 토큰입니다.  
  
 `pszTypename`  
 내보낼 정규화 된 형식 이름입니다.  
  
 `dwFlags`  
 `ComType` 와 같은 플래그 `tdPublic` 또는 `tdNested`합니다.  
  
 `pType`  
 내보내기 형식의 토큰을 받습니다. 이 중첩 된 형식을 내보내는에 필요 합니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 Alink.h 필요  
  
## <a name="see-also"></a>참고자료

- [IALink 인터페이스](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [IALink2 인터페이스](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [ALink API](../../../../docs/framework/unmanaged-api/alink/index.md)
