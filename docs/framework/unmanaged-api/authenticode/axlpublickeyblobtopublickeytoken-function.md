---
description: _AxlPublicKeyBlobToPublicKeyToken 함수에 대해 자세히 알아보세요.
title: _AxlPublicKeyBlobToPublicKeyToken 함수
ms.date: 03/30/2017
api_name:
- _AxlPublicKeyBlobToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 2d92a746-d68c-4f53-a16e-727f071a2d80
topic_type:
- apiref
ms.openlocfilehash: df0b484bad64051eb892d4898a6c90777cc2d5cf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781937"
---
# <a name="_axlpublickeyblobtopublickeytoken-function"></a>\_AxlPublicKeyBlobToPublicKeyToken 함수

CSP PUBLICKEYBLOB 형식에서 강력한 이름 공개 키 토큰을 계산합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT _AxlPublicKeyBlobToPublicKeyToken (
    [in]  PCCERT_CHAIN_CONTEXT   pCspPublicKeyBlob,
    [out] LPWSTR                 *ppwszPublicKeyToken
);
```

## <a name="parameters"></a>매개 변수

 `pCspPublicKeyBlob`\
 [in] CSP 공개 키 Blob입니다.

 `ppwszPublicKeyHash`\
 [out] 16진수로 인코딩된 공개 키 해시를 받는 WCHAR *에 대한 포인터입니다.

## <a name="return-value"></a>Return Value

 함수가 정상적으로 실행되는 경우 `S_OK`이고 그렇지 않으면 `S_FALSE`입니다.

## <a name="requirements"></a>요구 사항

**어셈블리**: clr.dll

## <a name="see-also"></a>참고 항목

- [Authenticode](index.md)
