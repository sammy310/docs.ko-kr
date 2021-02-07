---
description: '자세히 알아보기: ICorDebugController:: Continue 메서드'
title: ICorDebugController::Continue 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugController.Continue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Continue
helpviewer_keywords:
- Continue method [.NET Framework debugging]
- ICorDebugController::Continue method [.NET Framework debugging]
ms.assetid: 8684cd06-ad3e-48ef-832e-15320e1f43a2
topic_type:
- apiref
ms.openlocfilehash: e5858a8c287e8dd5a493a85c9f427ad8acd9ecc5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710805"
---
# <a name="icordebugcontrollercontinue-method"></a>ICorDebugController::Continue 메서드

[Stop 메서드](icordebugcontroller-stop-method.md)를 호출한 후 관리 되는 스레드의 실행을 다시 시작 합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT Continue (
    [in] BOOL fIsOutOfBand
);
```

## <a name="parameters"></a>매개 변수

`fIsOutOfBand`  
진행 `true` Out-of-band 이벤트에서 계속 하면로 설정 하 고, 그렇지 않으면로 설정 `false` 합니다.

## <a name="remarks"></a>설명

`Continue` 메서드를 호출한 후 프로세스를 계속 합니다 `ICorDebugController::Stop` .

혼합 모드 디버깅을 수행 하는 경우 `Continue` 대역 외 이벤트에서 계속 하지 않으면 Win32 이벤트 스레드에서를 호출 하지 마세요.

*대역내 이벤트* 는 관리 되는 이벤트 이거나 디버거가 프로세스의 관리 되는 상태와의 상호 작용을 지 원하는 동안 관리 되는 이벤트 또는 일반적인 관리 되지 않는 이벤트입니다. 이 경우 디버거는 매개 변수를로 설정 하 여 [ICorDebugUnmanagedCallback::D E버그 이벤트](icordebugunmanagedcallback-debugevent-method.md) 콜백을 수신 합니다 `fOutOfBand` `false` .

*Out-of-band 이벤트* 는 관리 되지 않는 이벤트로, 프로세스의 관리 되는 상태와의 상호 작용은 이벤트로 인해 중지 되는 동안에는 불가능 합니다. 이 경우 디버거는 `ICorDebugUnmanagedCallback::DebugEvent` `fOutOfBand` 매개 변수를로 설정 하 여 콜백을 받습니다 `true` .

## <a name="requirements"></a>요구 사항

**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.

**헤더:** CorDebug.idl, CorDebug.h

**라이브러리:** CorGuids.lib

**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
