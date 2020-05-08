---
title: ICorDebugEval::NewArray 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewArray
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewArray
helpviewer_keywords:
- NewArray method [.NET Framework debugging]
- ICorDebugEval::NewArray method [.NET Framework debugging]
ms.assetid: cc79a67d-5368-434d-a943-209db90491b9
topic_type:
- apiref
ms.openlocfilehash: 496a6a7e01dec8aa90ba4e849c431ccd499ef53d
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976202"
---
# <a name="icordebugevalnewarray-method"></a>ICorDebugEval::NewArray 메서드
지정 된 요소 형식 및 차원의 새 배열을 할당 합니다.  
  
 이 메서드는 .NET Framework 버전 2.0에서 사용 되지 않습니다. 대신 [ICorDebugEval2:: NewParameterizedArray](icordebugeval2-newparameterizedarray-method.md) 를 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT NewArray (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [in] ULONG32            rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `elementType`  
 진행 배열의 요소 형식을 지정 하는 CorElementType 열거형의 값입니다.  
  
 `pElementClass`  
 진행 요소의 클래스를 지정 하는 ICorDebugClass 개체에 대 한 포인터입니다. 요소 형식이 기본 형식인 경우이 값은 null 일 수 있습니다.  
  
 `rank`  
 진행 배열의 차원 수입니다. .NET Framework 2.0에서이 값은 1 이어야 합니다.  
  
 `dims`  
 진행 배열의 각 차원 크기 (바이트)입니다.  
  
 `lowBounds`  
 [in] 선택적 항목으로, 배열의 각 차원에 대 한 하 한입니다. 이 값을 생략 하면 각 차원에 대해 하 한이 0이 됩니다.  
  
## <a name="remarks"></a>설명  
 배열은 항상 스레드가 현재 실행 중인 응용 프로그램 도메인에 만들어집니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** 1.1, 1.0
