---
title: ISOSDacInterface::GetModuleData 메서드
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
ms.openlocfilehash: ed151f998ed7d28ba7ae170839ce2fa3a1ee6135
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57490452"
---
# <a name="isosdacinterfacegetmoduledata-method"></a>ISOSDacInterface::GetModuleData 메서드

주어진된 주소에 로드 된 모듈에 해당 데이터를 인출 합니다.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>구문

```
HRESULT GetModuleData(
    CLRDATA_ADDRESS moduleAddr,
    DacpModuleData *data
);
```

## <a name="parameters"></a>매개 변수

`moduleAddr`\
[in] 주소에 대 한 정보를 검색 하는 모듈입니다.

`data`\
[out] 합니다 [DacpModuleData 구조](dacpmoduledata-structure.md) 로드 된 모듈의 정보를 보관 합니다.


## <a name="remarks"></a>설명

제공 된 메서드는의 일부는 `ISOSDacInterface` 인터페이스 및 가상 메서드 테이블의 13 슬롯에 해당 합니다.

## <a name="requirements"></a>요구 사항

**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
**헤더:** 없음  
**라이브러리:** 없음  
**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>참고자료

- [디버깅](index.md)
- [ISOSDacInterface 인터페이스](isosdacinterface-interface.md)