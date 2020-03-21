---
title: IXCLR데이터 프로세스::에이엄메소드인스턴스바이트주소 방법
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: afc5fc377dd45d5e8d4d2d7b3385ca0524df69e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176658"
---
# <a name="ixclrdataprocessenummethodinstancebyaddress-method"></a>IXCLR데이터 프로세스::에이엄메소드인스턴스바이트주소 방법

주소 오프셋에서 시작하는 이 프로세스의 메서드 인스턴스를 모두보대해서는

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>구문

```cpp
HRESULT EnumMethodInstanceByAddress(
    [in] CLRDATA_ENUM              *handle,
    [out] IXCLRDataMethodInstance **method
);
```

## <a name="parameters"></a>매개 변수

`handle`\
【인】 메서드 인스턴스를 등록하기 위한 핸들입니다.

`mod`\
【아웃】 수온이 있는 메서드 인스턴스입니다.

## <a name="remarks"></a>설명

제공된 메서드는 `IXCLRDataProcess` 인터페이스의 일부이며 가상 메서드 테이블의 28번째 슬롯에 해당합니다.

## <a name="requirements"></a>요구 사항

**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.
**헤더:** 없음 **라이브러리:** **없음 .NET 프레임워크 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]

## <a name="see-also"></a>참고 항목

- [CLRDataSource유형 열거형](clrdatasourcetype-enumeration.md)
- [디버깅](index.md)
- [IXCLRDataProcess 인터페이스](ixclrdataprocess-interface.md)
