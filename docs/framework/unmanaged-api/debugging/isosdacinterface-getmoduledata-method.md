---
title: 'ISOSDacInterface:: GetModuleData 메서드'
ms.date: 02/01/2019
api.name:
- ISOSDacInterface::GetModuleData Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetModuleData Method
helpviewer.keywords:
- ISOSDacInterface::GetModuleData Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: b302100eb6cbfa83896cd358762c496ea01f7509
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420983"
---
# <a name="isosdacinterfacegetmoduledata-method"></a>ISOSDacInterface:: GetModuleData 메서드

지정 된 주소에서 로드 된 모듈에 해당 하는 데이터를 인출 합니다.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>구문

```cpp
HRESULT GetModuleData(
    CLRDATA_ADDRESS moduleAddr,
    DacpModuleData *data
);
```

## <a name="parameters"></a>매개 변수

`moduleAddr`\
진행 정보를 검색할 모듈의 주소입니다.

`data`\
제한이 로드 된 모듈의 정보를 저장할 [DacpModuleData 구조체](dacpmoduledata-structure.md) 입니다.

## <a name="remarks"></a>설명

제공 된 메서드는 인터페이스의 일부 이며 `ISOSDacInterface` 가상 메서드 테이블의 14 일 슬롯에 해당 합니다.

## <a name="requirements"></a>요구 사항

**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
**헤더:** 없음을  
**라이브러리:** 없음을  
**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>참고 항목

- [디버깅](index.md)
- [ISOSDacInterface 인터페이스](isosdacinterface-interface.md)
