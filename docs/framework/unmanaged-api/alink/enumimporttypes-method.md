---
description: '다음에 대 한 자세한 정보: EnumImportTypes 메서드'
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
ms.openlocfilehash: 39570740f3560f5bfef8ba80b95c0eb2aca41f59
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638121"
---
# <a name="enumimporttypes-method"></a>EnumImportTypes 메서드

각 범위에서 각 형식을 열거 합니다.

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
검색할 최대 형식 수입니다.

`aTypeDefs`\
는를 초과 하지 않는 형식 토큰을 받습니다 `dwMax` .

`pdwCount`\
에서 형식의 실제 수를 수신 `aTypeDefs` 합니다.

## <a name="return-value"></a>Return Value

메서드가 성공 하면 S_OK을 반환 합니다.

## <a name="requirements"></a>요구 사항

Alink 필요

## <a name="see-also"></a>참고 항목

- [IALink 인터페이스](ialink-interface.md)
- [IALink2 인터페이스](ialink2-interface.md)
- [ALink API](index.md)
