---
title: ICorDebugProcess4::P로케이스스테이트변경방법
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
ms.openlocfilehash: a6f36f5b86b4fa58ce2a4ef4aa23d527f797a5a5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178638"
---
# <a name="icordebugprocess4processstatechanged-method"></a>ICorDebugProcess4::P로케이스스테이트변경방법

ICorDebug 파이프라인에 프로세스 디버거에서 디버거가 debugee의 실행을 계속하고 있음을 알리고 있습니다.

## <a name="syntax"></a>구문

```cpp
HRESULT ProcessStateChanged(
    [in] CorDebugStateChange change
);
```

## <a name="parameters"></a>매개 변수

 `eChange`\
【인】 프로세스의 실행 상태의 변경을 설명하는 [CorDebugStateChange 열거형의](cordebugstatechange-enumeration.md) 멤버입니다.

## <a name="remarks"></a>설명

제공된 메서드는 `ICorDebugProcess4` 인터페이스의 일부이며 가상 메서드 테이블의 네 번째 슬롯에 해당합니다.

## <a name="requirements"></a>요구 사항

 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.

 **헤더:** 없음

 **라이브러리:** 없음

 **.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>참고 항목

- [ICorDebugProcess4 인터페이스](icordebugprocess4-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
- [디버깅](index.md)
