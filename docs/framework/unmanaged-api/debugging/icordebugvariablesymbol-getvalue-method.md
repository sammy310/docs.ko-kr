---
title: 'ICorDebugVariableSymbol:: GetValue 메서드'
ms.date: 03/30/2017
ms.assetid: 90abece1-392e-4ade-94a1-30c75b0f7074
ms.openlocfilehash: 5ef7e67efb2bafd9b9f52203246fd7d1590e6107
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120962"
---
# <a name="icordebugvariablesymbolgetvalue-method"></a>ICorDebugVariableSymbol:: GetValue 메서드
변수의 값을 바이트 배열로 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetValue(  
   [in] ULONG32 offset,  
   [in] ULONG32 cbContext,  
   [in, size_is(cbContext)] BYTE context[],  
   [in] ULONG32 cbValue,  
   [out] ULONG32 *pcbValue,  
   [out, size_is(cbValue), length_is(*pcbValue)] BYTE pValue[]  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `offset`  
 [in] 값을 읽을 변수의 시작 오프셋입니다. 이 매개 변수는 개체의 멤버 필드를 읽을 때 사용됩니다.  
  
 `cbContext`  
 [in] `context` 인수의 크기(바이트)입니다.  
  
 `context`  
 [in] 값을 읽는 데 사용되는 스레드 컨텍스트입니다.  
  
 `cbValue`  
 [in] `pValue` 버퍼의 크기(바이트)입니다.  
  
 `pcbValue`  
 [out] 실제로 `pValue` 버퍼에 기록되는 바이트 수입니다.  
  
 `pValue`  
 [out] 변수의 값을 포함하는 바이트 배열입니다.  
  
## <a name="remarks"></a>주의  
  
> [!NOTE]
> 이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugVariableSymbol 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
