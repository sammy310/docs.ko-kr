---
title: IMetaDataTables::GetUserString 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetUserString
helpviewer_keywords:
- IMetaDataTables::GetUserString method [.NET Framework metadata]
- GetUserString method, IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 35b8f0d6-9aba-4714-adb2-62020a38fb7e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0fefbab6b2ea9fbbfd90e03c41578a924f99c7a0
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364166"
---
# <a name="imetadatatablesgetuserstring-method"></a>IMetaDataTables::GetUserString 메서드

현재 범위의 문자열 열에 지정된 된 인덱스에 하드 코드 된 문자열을 가져옵니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetUserString (
    [in]  ULONG       ixUserString,
    [out] ULONG       *pcbData,
    [out] const void  **ppData
);
```

## <a name="parameters"></a>매개 변수

`ixUserString`\
[in] 하드 코드 된 문자열을 검색할 인덱스 값입니다.

`pcbData`\
[out] 크기에 대 한 포인터 `ppData`합니다.

`ppData`\
[out] 반환된 된 문자열에 대 한 포인터에 대 한 포인터입니다.

## <a name="requirements"></a>요구 사항

**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.

**헤더:** Cor.h

**라이브러리:** MsCorEE.dll에서 리소스로 사용

**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>참고자료

- [IMetaDataTables 인터페이스](imetadatatables-interface.md)
- [IMetaDataTables2 인터페이스](imetadatatables2-interface.md)