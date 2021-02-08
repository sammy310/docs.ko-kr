---
description: '자세히 알아보기: CertFreeAuthenticodeSignerInfo 함수'
title: CertFreeAuthenticodeSignerInfo 함수
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeSignerInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 8029633c-b6e4-4665-a7c2-89607c3247ef
topic_type:
- apiref
ms.openlocfilehash: 6e8a97e8fee37d885c7d32102ed8cc7654992223
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772980"
---
# <a name="certfreeauthenticodesignerinfo-function"></a>CertFreeAuthenticodeSignerInfo 함수

[AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) 구조에 할당 된 리소스를 해제 합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT CertFreeAuthenticodeSignerInfo (
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);
```

## <a name="parameters"></a>매개 변수

 `pSignerInfo`\
 [in, out] 해제할 서명자 정보입니다. [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) 구조체를 참조 하세요.

## <a name="return-value"></a>Return Value

 함수가 정상적으로 실행되는 경우 `S_OK`입니다. 그러지 않으면 오류 코드가 반환됩니다.

## <a name="requirements"></a>요구 사항

**어셈블리**: clr.dll

## <a name="see-also"></a>참고 항목

- [Authenticode](index.md)
