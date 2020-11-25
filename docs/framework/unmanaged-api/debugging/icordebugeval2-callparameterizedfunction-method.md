---
title: ICorDebugEval2::CallParameterizedFunction 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.CallParameterizedFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::CallParameterizedFunction
helpviewer_keywords:
- ICorDebugEval2::CallParameterizedFunction method [.NET Framework debugging]
- CallParameterizedFunction method [.NET Framework debugging]
ms.assetid: 72f54a45-dbe6-4bb4-8c99-e879a27368e5
topic_type:
- apiref
ms.openlocfilehash: c36dec80b6885b0ee56670b94dbd0b155a9710b4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729709"
---
# <a name="icordebugeval2callparameterizedfunction-method"></a>ICorDebugEval2::CallParameterizedFunction 메서드

생성자가 <xref:System.Type> 매개 변수를 사용 하거나 매개 변수를 사용할 수 있는 클래스 내에 중첩 될 수 있는 지정 된 ICorDebugFunction에 대 한 호출을 설정 합니다 <xref:System.Type> .  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CallParameterizedFunction (  
    [in] ICorDebugFunction     *pFunction,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pFunction`  
 진행 호출할 함수를 나타내는 개체에 대 한 포인터입니다 `ICorDebugFunction` .  
  
 `nTypeArgs`  
 진행 함수가 사용 하는 인수 개수입니다.  
  
 `ppTypeArgs`  
 진행 각각 함수 인수를 나타내는 ICorDebugType 개체를 가리키는 포인터의 배열입니다.  
  
 `nArgs`  
 진행 함수에 전달 된 값의 수입니다.  
  
 `ppArgs`  
 진행 각각 함수 인수에 전달 된 값을 나타내는 ICorDebugValue 개체를 가리키는 포인터의 배열입니다.  
  
## <a name="remarks"></a>설명  

 `CallParameterizedFunction` 함수는 형식 매개 변수가 있는 클래스 내부에 있을 수 있다는 점을 제외 하 고는 [ICorDebugEval:: CallFunction](icordebugeval-callfunction-method.md) 과 유사 합니다. 즉, 형식 매개 변수를 사용 하거나 둘 다를 사용할 수 있습니다. 먼저 클래스에 대해 형식 인수를 지정 하 고 그 다음에 함수를 지정 해야 합니다.  
  
 함수가 다른 응용 프로그램 도메인에 있는 경우 전환이 수행 됩니다. 그러나 모든 형식 및 값 인수는 대상 응용 프로그램 도메인에 있어야 합니다.  
  
 함수 실행은 제한 된 시나리오 에서만 수행할 수 있습니다. `CallParameterizedFunction`또는이 `ICorDebugEval::CallFunction` 실패할 경우 반환 되는 HRESULT는 가장 일반적인 실패 이유를 표시 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
