---
description: '자세히 알아보기: ICorDebugCode:: GetVersionNumber 메서드'
title: ICorDebugCode::GetVersionNumber 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetVersionNumber
helpviewer_keywords:
- GetVersionNumber method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetVersionNumber method [.NET Framework debugging]
ms.assetid: c8e02518-679f-4e9f-8a28-ba4a89a3876f
topic_type:
- apiref
ms.openlocfilehash: 901342333bea3d455407602dde78bdccd0140d77
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764907"
---
# <a name="icordebugcodegetversionnumber-method"></a>ICorDebugCode::GetVersionNumber 메서드

이 "ICorDebugCode"가 나타내는 코드의 버전을 식별 하는 1부터 사용 하는 번호를 가져옵니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetVersionNumber (
    [out] ULONG32    *nVersion
);
```

## <a name="parameters"></a>매개 변수

 `nVersion`  
 제한이 코드의 버전 번호에 대 한 포인터입니다.

## <a name="remarks"></a>설명

 코드에서 편집 하며 계속 하기 (EnC) 작업이 수행 될 때마다 버전 번호가 증가 합니다.

## <a name="requirements"></a>요구 사항

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
