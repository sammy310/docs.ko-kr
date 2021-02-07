---
description: '자세히 알아보기: DacpModuleData Structure'
title: DacpModuleData 구조체
ms.date: 02/01/2019
api.name:
- DacpModuleData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpModuleData Structure
helpviewer.keywords:
- DacpModuleData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 376a49ab78db08e5906e8d33389cdc45fe76e81e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661586"
---
# <a name="dacpmoduledata-structure"></a>DacpModuleData 구조체

모듈의 런타임 정보에 대 한 전송 버퍼를 정의 합니다.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>구문

```cpp
struct DacpModuleData
{
    CLRDATA_ADDRESS Address;
    CLRDATA_ADDRESS File;
    CLRDATA_ADDRESS  ilBase;
    char payLoad[132];
};
```

## <a name="members"></a>구성원

| 멤버    | 설명                                                             |
| --------- | ----------------------------------------------------------------------- |
| `Address` | 모듈 개체의 주소입니다.                                           |
| `File`    | PE (이식 가능한 실행) 파일에 대 한 포인터입니다.                       |
| `ilBase`  | 로드 된 이미지의 기본 주소입니다.                                 |
| `payLoad` | 런타임에서 사용 하는 추가 모듈 정보에 대 한 페이로드 버퍼입니다. |

## <a name="remarks"></a>설명

이 구조체는 런타임 내에 있으며 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다. 이를 사용 하려면 위에 지정 된 대로 구조를 정의 합니다.

## <a name="requirements"></a>요구 사항

**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
**헤더:** 없음을  
**라이브러리:** 없음을  
**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>참고 항목

- [디버깅](index.md)
- [디버깅 구조체](debugging-structures.md)
