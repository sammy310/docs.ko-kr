---
title: GetHashFromBlob 함수
ms.date: 03/30/2017
api_name:
- GetHashFromBlob
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromBlob
helpviewer_keywords:
- GetHashFromBlob function [.NET Framework strong naming]
ms.assetid: b712d862-f2d0-4b55-87d4-65bbeadef982
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d9e7b52c9061a1a7b470f9d4abf735e605087dc
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352076"
---
# <a name="gethashfromblob-function"></a>GetHashFromBlob 함수

지정된 해시 알고리즘을 사용하여 지정된 메모리 주소에 있는 어셈블리의 해시를 가져옵니다.

이 함수는 더 이상 사용 되지 않습니다. 사용 된 [iclrstrongname:: Gethashfromblob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md) 메서드 대신 합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetHashFromBlob (
    [in]  BYTE    *pbBlob,
    [in]  DWORD   cchBlob,
    [in, out] unsigned int   *piHashAlg,
    [out] BYTE    *pbHash,
    [in]  DWORD   cchHash,
    [out] DWORD   *pchHash
);
```

## <a name="parameters"></a>매개 변수

`pbBlob`\
[in] 해시할 메모리 블록의 주소에 대 한 포인터입니다.

`cchBlob`\
[in] 메모리 블록의 길이 (바이트) 합니다.

`piHashAlg`\
[out에서] 해시 알고리즘을 지정 하는 상수입니다. 기본 알고리즘에 0을 사용 합니다.

`pbHash`\
[out] 반환 된 해시 버퍼입니다.

`cchHash`\
[in] 요청 된 최대 크기인 `pbHash`합니다.

`pchHash`\
[out] 반환 된 바이트의 크기, `pbHash`합니다.

## <a name="requirements"></a>요구 사항

**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.

**헤더:** StrongName.h

**라이브러리:** MsCorEE.dll에 리소스로 포함

**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>참고자료

- [GetHashFromBlob 메서드](../hosting/iclrstrongname-gethashfromblob-method.md)
- [ICLRStrongName 인터페이스](../hosting/iclrstrongname-interface.md)