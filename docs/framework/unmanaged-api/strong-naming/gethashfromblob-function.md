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
ms.openlocfilehash: d1027aea1d800bda1654b223fec992aa70efd4b7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140720"
---
# <a name="gethashfromblob-function"></a>GetHashFromBlob 함수

지정된 해시 알고리즘을 사용하여 지정된 메모리 주소에 있는 어셈블리의 해시를 가져옵니다.

이 함수는 더 이상 사용 되지 않습니다. 대신 [ICLRStrongName:: GetHashFromBlob](../hosting/iclrstrongname-gethashfromblob-method.md) 메서드를 사용 합니다.

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
진행 해시할 메모리 블록의 주소에 대 한 포인터입니다.

`cchBlob`\
진행 메모리 블록의 길이 (바이트)입니다.

`piHashAlg`\
[in, out] 해시 알고리즘을 지정 하는 상수입니다. 기본 알고리즘에는 0을 사용 합니다.

`pbHash`\
제한이 반환 된 해시 버퍼입니다.

`cchHash`\
진행 `pbHash`요청 된 최대 크기입니다.

`pchHash`\
제한이 반환 된 `pbHash`의 크기 (바이트)입니다.

## <a name="requirements"></a>요구 사항

**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.

**헤더:** StrongName

**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.

**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>참조

- [GetHashFromBlob 메서드](../hosting/iclrstrongname-gethashfromblob-method.md)
- [ICLRStrongName 인터페이스](../hosting/iclrstrongname-interface.md)
