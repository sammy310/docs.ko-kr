---
description: '자세히 알아보기: IMetaDataTables:: GetUserString 메서드'
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
ms.openlocfilehash: 0909bfb2dbf4e6a34b746da7397a82845c2129c2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99687690"
---
# <a name="imetadatatablesgetuserstring-method"></a>IMetaDataTables::GetUserString 메서드

현재 범위에 있는 문자열 열의 지정 된 인덱스에서 하드 코드 된 문자열을 가져옵니다.

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
진행 하드 코딩 된 문자열이 검색 되는 인덱스 값입니다.

`pcbData`\
제한이 의 크기에 대 한 포인터입니다 `ppData` .

`ppData`\
제한이 반환 된 문자열에 대 한 포인터에 대 한 포인터입니다.

## <a name="requirements"></a>요구 사항

**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.

**헤더:** Cor

**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.

**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>참고 항목

- [IMetaDataTables 인터페이스](imetadatatables-interface.md)
- [IMetaDataTables2 인터페이스](imetadatatables2-interface.md)
