---
title: 'IXCLRDataMethodDefinition:: StartEnumInstances 메서드'
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::StartEnumInstances Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::StartEnumInstances Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::StartEnumInstances Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: b0c37c666f23f04239ed827246b87c43ee8d5ad9
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420931"
---
# <a name="ixclrdatamethoddefinitionstartenuminstances-method"></a>IXCLRDataMethodDefinition:: StartEnumInstances 메서드

지정 된에 대 한 메서드 인스턴스의 열거형 핸들을 제공 `IXCLRDataAppDomain` 합니다.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>구문

```cpp
HRESULT StartEnumInstances(
    [in] IXCLRDataAppDomain* appDomain,
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a>매개 변수

`appDomain`\
진행 열거를 위한 AppDomain입니다.

`handle`\
제한이 인스턴스를 열거 하는 핸들입니다.

## <a name="remarks"></a>설명

제공 된 메서드는 인터페이스의 일부 `IXCLRDataMethodDefinition` 이며 가상 메서드 테이블의 5 번째 슬롯에 해당 합니다.

## <a name="requirements"></a>요구 사항

**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
**헤더:** 없음을  
**라이브러리:** 없음을  
**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>참고 항목

- [CLRDataSourceType 열거형](clrdatasourcetype-enumeration.md)
- [디버깅](index.md)
- [IXCLRDataMethodDefinition 인터페이스](ixclrdatamethoddefinition-interface.md)
