---
title: DacpGetModuleAddress::Request 메서드
ms.date: 01/16/2019
api.name:
- DacpGetModuleAddress::Request Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpGetModuleAddress::Request Method
helpviewer.keywords:
- DacpGetModuleAddress::Request Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 1755526636bed6d78663112e4c2ad5ab7c3f731c
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860845"
---
# <a name="dacpgetmoduleaddressrequest-method"></a>DacpGetModuleAddress::Request 메서드

지정 된 런타임 구조체에서 구조체를 채우도록 요청을 수행 합니다.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>구문

```cpp
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a>매개 변수

`pDataModule`\
진행 초기값 데이터 모듈에 대 한 포인터입니다.

## <a name="remarks"></a>설명

이 구조체는 런타임 내에 있으며 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다. 이를 사용 하는 가장 쉬운 방법은 구현을 모방 하는 것입니다.

- 다음 매개 변수를 사용 하 여 `Request` `IXCLRDataModule*` 매개 변수에 대해 메서드를 호출 하 여 가져온 값을 반환 합니다.`((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`

## <a name="requirements"></a>요구 사항

**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md) 을 참조 하세요.\
**헤더:** 없음을
**라이브러리:** 없음을
**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]

## <a name="see-also"></a>참고 항목

- [디버깅](index.md)
- [DacpGetModuleAddress 구조체](dacpgetmoduleaddress-structure.md)
