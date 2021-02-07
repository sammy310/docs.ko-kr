---
description: '자세히 알아보기: ICorDebugVariableHome:: GetArgumentIndex 메서드'
title: 'ICorDebugVariableHome:: GetArgumentIndex 메서드'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetArgumentIndex
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetArgumentIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetArgumentIndex method [.NET Framework debugging]
- GetArgumentIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: e86fcc72-388d-4009-ab21-8f9c3323e9a3
topic_type:
- apiref
ms.openlocfilehash: 827ef55d3e3509cbfbfc8213ef5b53fbe2e2220e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690043"
---
# <a name="icordebugvariablehomegetargumentindex-method"></a>ICorDebugVariableHome:: GetArgumentIndex 메서드

함수 인수의 인덱스를 가져옵니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetArgumentIndex(
    [out] ULONG32* pArgumentIndex
);
```

## <a name="parameters"></a>매개 변수

`pArgumentIndex`\
제한이 인수 인덱스에 대 한 포인터입니다.

## <a name="return-value"></a>Return Value

메서드는 다음 값을 반환 합니다.

|값|설명|
|-----------|-----------------|
|`S_OK`|메서드 호출에서 유효한 인수 인덱스를 반환 했습니다.|
|`E_FAIL`|현재 [ICorDebugVariableHome](icordebugvariablehome-interface.md) 인스턴스는 지역 변수를 나타냅니다.|

## <a name="remarks"></a>설명

인수 인덱스는이 인수에 대 한 메타 데이터를 검색 하는 데 사용할 수 있습니다.

## <a name="requirements"></a>요구 사항

**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.

**헤더:** CorDebug.idl, CorDebug.h

**라이브러리:** CorGuids.lib

**.NET Framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]

## <a name="see-also"></a>참고 항목

- [ICorDebugVariableHome 인터페이스](icordebugvariablehome-interface.md)
