---
description: '자세히 알아보기: CertFreeAuthenticodeTimestamperInfo 함수'
title: CertFreeAuthenticodeTimestamperInfo 함수
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeTimestamperInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 3eb14c49-68c2-4516-ac89-e5bd7473831c
topic_type:
- apiref
ms.openlocfilehash: 5234a90ea1d0272a7409b1b0b4def2160b77a513
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772941"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a>CertFreeAuthenticodeTimestamperInfo 함수

[AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) 구조에 할당 된 리소스를 해제 합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT CertFreeAuthenticodeTimestamperInfo (
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo
);
```

## <a name="parameters"></a>매개 변수

 `pTimestamperInfo`\
 [in, out] 해제할 타임스탬퍼 정보입니다. [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) 구조체를 참조 하세요.

## <a name="return-value"></a>Return Value

 함수가 정상적으로 실행되는 경우 `S_OK`입니다. 그러지 않으면 오류 코드가 반환됩니다.

## <a name="requirements"></a>요구 사항

**어셈블리**: clr.dll

## <a name="see-also"></a>참고 항목

- [Authenticode](index.md)
