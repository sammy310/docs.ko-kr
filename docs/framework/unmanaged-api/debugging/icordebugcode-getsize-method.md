---
title: ICorDebugCode::GetSize 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetSize method [.NET Framework debugging]
ms.assetid: 115bc6de-f5e2-4e8e-bb38-c7cf54045434
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 25349f7c8274b818df2cd1bc5d67856e31efecc4
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395541"
---
# <a name="icordebugcodegetsize-method"></a>ICorDebugCode::GetSize 메서드

이 "ICorDebugCode"로 표시 되는 이진 코드의 크기 (바이트)를 가져옵니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetSize (
    [out] ULONG32    *pcBytes
);
```

## <a name="parameters"></a>매개 변수

`pcBytes`  
제한이 이 `ICorDebugCode` 개체가 나타내는 이진 코드의 크기 (바이트)에 대 한 포인터입니다.

## <a name="requirements"></a>요구 사항

**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.

**헤더:** CorDebug.idl, CorDebug.h

**라이브러리:** CorGuids.lib

**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
