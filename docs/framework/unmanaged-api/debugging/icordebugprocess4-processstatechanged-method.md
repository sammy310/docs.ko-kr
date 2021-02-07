---
description: ICorDebugProcess4::P rocessStateChanged 메서드에 대해 자세히 알아보세요.
title: ICorDebugProcess4::P rocessStateChanged 메서드
ms.date: 02/07/2019
api_name:
- ICorDebugProcess4::ProcessStateChanged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess4::ProcessStateChanged
helpviewer_keywords:
- ICorDebugProcess4::ProcessStateChanged method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 35a76b3c6dd9b37d3f06f23bc2ffea82f125a29e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746473"
---
# <a name="icordebugprocess4processstatechanged-method"></a>ICorDebugProcess4::P rocessStateChanged 메서드

ICorDebug 파이프라인에 out of process 디버거가 디버기의의 실행을 계속 진행 중임을 알립니다.

## <a name="syntax"></a>구문

```cpp
HRESULT ProcessStateChanged(
    [in] CorDebugStateChange change
);
```

## <a name="parameters"></a>매개 변수

 `eChange`\
진행 프로세스 실행 상태의 변경을 설명 하는 [CorDebugStateChange 열거형](cordebugstatechange-enumeration.md) 의 멤버입니다.

## <a name="remarks"></a>설명

제공 된 메서드는 인터페이스의 일부 `ICorDebugProcess4` 이며 가상 메서드 테이블의 네 번째 슬롯에 해당 합니다.

## <a name="requirements"></a>요구 사항

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.

 **헤더:** 없음을

 **라이브러리:** 없음을

 **.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>참고 항목

- [ICorDebugProcess4 인터페이스](icordebugprocess4-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
- [디버깅](index.md)
