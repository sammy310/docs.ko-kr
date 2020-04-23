---
title: DacpGetModuleAddress::요청 방법
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
ms.openlocfilehash: 4dbe6a2c295e5afae1b6761f0c7b695fdb906428
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102909"
---
# <a name="dacpgetmoduleaddressrequest-method"></a>DacpGetModuleAddress::요청 방법

지정된 런타임 구조에서 구조를 채우는 요청을 수행합니다.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>구문

```cpp
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a>매개 변수

`pDataModule`\
【인】 시드 데이터 모듈에 대한 포인터입니다.

## <a name="remarks"></a>설명

이 구조는 런타임 내에 있으며 헤더 나 라이브러리 파일을 통해 노출되지 않습니다. 이를 사용하는 가장 쉬운 방법은 구현을 모방하는 것입니다.

- 다음 매개 변수를 사용하여 `Request` 매개 `IXCLRDataModule*` 변수에서 메서드를 호출하여 얻은 값을 반환합니다.`((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`

## <a name="requirements"></a>요구 사항

**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md) 보기\
**헤더:** 없음\
**라이브러리:** 없음\
**.NET 프레임워크 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]

## <a name="see-also"></a>참고 항목

- [디버깅](index.md)
- [DacpGet모듈주소 구조](dacpgetmoduleaddress-structure.md)
