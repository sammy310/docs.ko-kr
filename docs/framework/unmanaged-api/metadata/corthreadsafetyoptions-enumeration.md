---
title: CorThreadSafetyOptions 열거형
ms.date: 03/30/2017
api_name:
- CorThreadSafetyOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorThreadSafetyOptions
helpviewer_keywords:
- CorThreadSafetyOptions enumeration [.NET Framework metadata]
ms.assetid: dae07d9b-df51-488c-b17e-52d6e48217bd
topic_type:
- apiref
ms.openlocfilehash: 93dd8c56176890d04d792f3c336492e4f232825b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442475"
---
# <a name="corthreadsafetyoptions-enumeration"></a>CorThreadSafetyOptions 열거형

스레드 안정성 옵션을 선택하는 플래그를 지정합니다.

## <a name="syntax"></a>구문

```cpp
typedef enum CorThreadSafetyOptions {
    MDThreadSafetyDefault       = 0x00000000,
    MDThreadSafetyOff           = 0x00000000,
    MDThreadSafetyOn            = 0x00000001,
} CorThreadSafetyOptions;
```

## <a name="members"></a>멤버

|멤버|설명|
|------------|-----------------|
|`MDThreadSafetyDefault`|기본 값입니다. `MDThreadSafetyOff`와 동일합니다.|
|`MDThreadSafetyOff`|판독기/작성기 잠금을 설정할 수 없음을 나타냅니다.|
|`MDThreadSafetyOn`|판독기/작성기 잠금을 설정할 수 있음을 나타냅니다.|

## <a name="requirements"></a>요구 사항

**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.

**헤더:** CorHdr .h

**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>참고자료

- [메타데이터 열거형](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
