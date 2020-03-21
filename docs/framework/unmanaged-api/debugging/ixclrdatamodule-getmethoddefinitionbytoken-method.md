---
title: IXCLR데이터 모듈::GetMethod정의토큰 방법
ms.date: 01/16/2019
api.name:
- IXCLRDataModule::GetMethodDefinitionByToken Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule::GetMethodDefinitionByToken Method
helpviewer.keywords:
- IXCLRDataModule::GetMethodDefinitionByToken Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 294c5340caf2217f9337d654a11a63a43d46febd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176671"
---
# <a name="ixclrdatamodulegetmethoddefinitionbytoken-method"></a>IXCLR데이터 모듈::GetMethod정의토큰 방법

지정된 메타데이터 토큰에 해당하는 메서드 정의를 가져옵니다.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>구문

```cpp
HRESULT GetMethodDefinitionByToken(
    [in] mdMethodDef token,
    [out] IXCLRDataMethodDefinition** methodDefinition
);
```

## <a name="parameters"></a>매개 변수

`token`\
【인】 메서드 토큰입니다.

`methodDefinition`\
【아웃】 메서드 정의입니다.

## <a name="remarks"></a>설명

제공된 메서드는 `IXCLRDataModule` 인터페이스의 일부이며 가상 메서드 테이블의 25번째 슬롯에 해당합니다.

## <a name="requirements"></a>요구 사항

**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
**헤더:** 없음  
**라이브러리:** 없음  
**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>참고 항목

- [디버깅](index.md)
- [IXCLRDataModule 인터페이스](ixclrdatamodule-interface.md)
