---
description: '자세히 알아보기: ICorDebugCode:: IsIL 메서드'
title: ICorDebugCode::IsIL 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugCode.IsIL
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::IsIL
helpviewer_keywords:
- ICorDebugCode::IsIL method [.NET Framework debugging]
- IsIL method [.NET Framework debugging]
ms.assetid: 132ef8cc-d938-43f3-b8f2-e3b97c0ceb33
topic_type:
- apiref
ms.openlocfilehash: db41f9ebaa6a6403b21e10d1daa0e8b167c7cb96
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711128"
---
# <a name="icordebugcodeisil-method"></a>ICorDebugCode::IsIL 메서드

이 "ICorDebugCode"가 MSIL (Microsoft 중간 언어)로 컴파일된 코드를 나타내는지 여부를 나타내는 값을 가져옵니다.

## <a name="syntax"></a>구문

```cpp
HRESULT IsIL (
    [out] BOOL       *pbIL
);
```

## <a name="parameters"></a>매개 변수

`pbIL`  
[out] `true` 이가 `ICorDebugCode` MSIL로 컴파일된 코드를 나타내면이 고, 그렇지 않으면 `false` 입니다.

## <a name="requirements"></a>요구 사항

**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.

**헤더:** CorDebug.idl, CorDebug.h

**라이브러리:** CorGuids.lib

**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
