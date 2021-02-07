---
description: '자세히 알아보기: ICorDebugCode2:: GetCompilerFlags 메서드'
title: ICorDebugCode2::GetCompilerFlags 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugCode2.GetCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2::GetCompilerFlags
helpviewer_keywords:
- GetCompilerFlags method [.NET Framework debugging]
- ICorDebugCode2::GetCompilerFlags method [.NET Framework debugging]
ms.assetid: 532e9dfd-d114-4c75-b952-1accce102643
topic_type:
- apiref
ms.openlocfilehash: 820b6d2392b2b91bbfc8a85b165c4d73a2546859
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711121"
---
# <a name="icordebugcode2getcompilerflags-method"></a>ICorDebugCode2::GetCompilerFlags 메서드

이 코드 개체가 네이티브 이미지 생성기 (Ngen.exe)를 사용 하 여 컴파일 또는 생성 된 JIT (just-in-time) 인 조건을 지정 하는 플래그를 가져옵니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetCompilerFlags (
    [out] DWORD *pdwFlags
);
```

## <a name="parameters"></a>매개 변수

`pdwFlags`  
제한이 JIT 컴파일러 또는 네이티브 이미지 생성기의 동작을 지정 하는 [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) 열거형의 값에 대 한 포인터입니다.

## <a name="requirements"></a>요구 사항

**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.

**헤더:** CorDebug.idl, CorDebug.h

**라이브러리:** CorGuids.lib

**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
