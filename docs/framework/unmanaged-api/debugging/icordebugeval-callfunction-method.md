---
title: ICorDebugEval::CallFunction 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval.CallFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::CallFunction
helpviewer_keywords:
- ICorDebugEval::CallFunction method [.NET Framework debugging]
- CallFunction method [.NET Framework debugging]
ms.assetid: 7f470c5c-e1c0-4d8d-aad8-830f113ae751
topic_type:
- apiref
ms.openlocfilehash: 4ac26ef4449dc02230f26b1247616b4587d217b7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73085166"
---
# <a name="icordebugevalcallfunction-method"></a>ICorDebugEval::CallFunction 메서드

지정 된 함수에 대 한 호출을 설정 합니다.

이 메서드는 .NET Framework 버전 2.0에서 사용 되지 않습니다. 대신 [ICorDebugEval2:: CallParameterizedFunction](icordebugeval2-callparameterizedfunction-method.md) 을 사용 합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT CallFunction (
    [in] ICorDebugFunction  *pFunction,
    [in] ULONG32            nArgs,
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]
);
```

## <a name="parameters"></a>매개 변수

`pFunction`\
진행 호출할 함수를 지정 하는 ICorDebugFunction 개체에 대 한 포인터입니다.

`nArgs`\
진행 함수에 대 한 인수 개수입니다.

`ppArgs`\
진행 각각 함수에 전달 될 인수를 지정 하는 ICorDebugValue 개체를 가리키는 포인터의 배열입니다.

## <a name="remarks"></a>주의

함수가 virtual 인 경우 `CallFunction`는 가상 디스패치를 수행 합니다. 함수가 다른 응용 프로그램 도메인에 있는 경우 모든 인수가 해당 응용 프로그램 도메인에 있는 경우에만 전환이 수행 됩니다.

## <a name="requirements"></a>요구 사항

**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.

**헤더:** CorDebug.idl, CorDebug.h

**라이브러리:** CorGuids.lib

**.NET Framework 버전:** 1.1, 1.0

## <a name="see-also"></a>참조

- [CallParameterizedFunction 메서드](icordebugeval2-callparameterizedfunction-method.md)
