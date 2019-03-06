---
title: EnumImportTypes 메서드
ms.date: 03/30/2017
api_name:
- EnumImportTypes
- IALink.EnumImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumImportTypes
helpviewer_keywords:
- EnumImportTypes method
ms.assetid: 83a0e4e7-ec06-40cb-9b63-700b9695bb04
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1d0aefea7345bc3bf37bdb8d13cb2cda19cfe527
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355742"
---
# <a name="enumimporttypes-method"></a>EnumImportTypes 메서드

각 범위에서 각 종류를 열거합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT EnumImportTypes(
    HALINKENUM   hEnum,
    DWORD        dwMax,
    mdTypeDef    aTypeDefs[],
    DWORD*       pdwCount
) PURE;
```

## <a name="parameters"></a>매개 변수

`hEnum`\
열거자에 대 한 핸들입니다.

`dwMax`\
최대 검색 하는 형식입니다.

`aTypeDefs`\
넘지 형식 토큰을 받는 `dwMax`합니다.

`pdwCount`\
실제 수를 입력 받는 `aTypeDefs`합니다.

## <a name="return-value"></a>반환 값

메서드가 성공 하면 S_OK를 반환 합니다.

## <a name="requirements"></a>요구 사항

Alink.h 필요

## <a name="see-also"></a>참고자료

- [IALink 인터페이스](ialink-interface.md)
- [IALink2 인터페이스](ialink2-interface.md)
- [ALink API](index.md)