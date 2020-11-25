---
title: DacpGetModuleAddress 구조체
ms.date: 01/16/2019
api.name:
- DacpGetModuleAddress Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpGetModuleAddress Structure
helpviewer.keywords:
- DacpGetModuleAddress Structure [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: a65fa9974165fa36e59a7fb83dca6dd902f7d8dc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724397"
---
# <a name="dacpgetmoduleaddress-structure"></a>DacpGetModuleAddress 구조체

모듈 주소 요청에 대 한 컨테이너를 정의 합니다.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>구문

```cpp
struct DacpGetModuleAddress
{
    CLRDATA_ADDRESS ModulePtr;
};
```

## <a name="members"></a>멤버

| 멤버      | 설명                |
| ----------- | -------------------------- |
| `ModulePtr` | 모듈에 대 한 포인터입니다. |

## <a name="methods"></a>메서드

| 메서드                                                                                               | 설명                                                                    |
| ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| [요청](dacpgetmoduleaddress-request-method.md) | 지정 된 런타임 구조체에서 구조체를 채우도록 요청을 수행 합니다. |

## <a name="remarks"></a>설명

이 구조체는 런타임 내에 있으며 헤더 또는 라이브러리 파일을 통해 노출 되지 않습니다. 이를 사용 하려면 위에 지정 된 대로 구조를 정의 합니다 `CLRDATA_ADDRESS` . 여기서은 64 비트의 부호 없는 정수입니다.

## <a name="requirements"></a>요구 사항

**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
**헤더:** 없음을  
**라이브러리:** 없음을  
**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>참조

- [디버깅](index.md)
- [디버깅 구조체](debugging-structures.md)
