---
description: _AxlRSAKeyValueToPublicKeyToken 함수에 대해 자세히 알아보세요.
title: _AxlRSAKeyValueToPublicKeyToken 함수
ms.date: 03/30/2017
api_name:
- _AxlRSAKeyValueToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: d60f19fe-7bec-47ba-b60e-ba9ce66abf8c
topic_type:
- apiref
ms.openlocfilehash: 01fc4cdc1d9985375748307ca2d7fff97191c908
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747272"
---
# <a name="_axlrsakeyvaluetopublickeytoken-function"></a>\_AxlRSAKeyValueToPublicKeyToken 함수

모듈러스 및 지수를 강력한 이름 공개 키 토큰으로 변환합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT _AxlRSAKeyValueToPublicKeyToken (
    [in]  PCRYPT_DATA_BLOB pModulusBlob,
    [in]  PCRYPT_DATA_BLOB pExponentBlob,
    [out] LPWSTR           *ppwszPublicKeyToken
);
```

## <a name="parameters"></a>매개 변수

 `pModulusBlob`\
 진행 A s e 64로 인코딩된 모듈러스 blob ( \<Modulus> 요소)입니다.  [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) 구조체를 참조 하세요.

 `pExponentBlob`\
 진행 A s e 64로 인코딩된 지 수 blob ( \<Exponent> 요소)입니다. [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) 구조체를 참조 하세요.

 `ppwszPublicKeyToken`\
 [out] 16진수로 인코딩된 공개 키 토큰을 받는 WCHAR *에 대한 포인터입니다.

## <a name="return-value"></a>Return Value

 함수가 정상적으로 실행되는 경우 `S_OK`입니다. 그러지 않으면 오류 코드가 반환됩니다.

## <a name="requirements"></a>요구 사항

**어셈블리**: clr.dll

## <a name="see-also"></a>참고 항목

- [Authenticode](index.md)
