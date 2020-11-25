---
title: ICorDebugFunction2::GetVersionNumber 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.GetVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::GetVersionNumber
helpviewer_keywords:
- ICorDebugFunction2::GetVersionNumber method [.NET Framework debugging]
- GetVersionNumber method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: e3a1ce48-9bb9-4ed6-a5fe-5e1819a6333f
topic_type:
- apiref
ms.openlocfilehash: 88fb205235cfaf3566fbd74b05a4e9833058f4a0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696104"
---
# <a name="icordebugfunction2getversionnumber-method"></a>ICorDebugFunction2::GetVersionNumber 메서드

이 함수의 편집 하며 계속 하기 버전을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetVersionNumber (  
    [out] ULONG32   *pnVersion  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pnVersion`  
 제한이 이 ICorDebugFunction2 개체가 나타내는 함수의 버전 번호를 나타내는 정수에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 런타임은 디버그 세션 중에 각 모듈에 수행 된 편집 횟수를 추적 합니다. 함수의 버전 번호는 함수를 도입 하는 편집의 수보다 하나 이상입니다. 함수의 원래 버전이 버전 1입니다. 이 모듈에 대해 [ICorDebugModule2:: ApplyChanges](icordebugmodule2-applychanges-method.md) 가 호출 될 때마다 모듈의 숫자가 증가 합니다. 따라서 함수의 본문이 첫 번째 및 세 번째 호출에서 대체 된 경우 `ICorDebugModule2::ApplyChanges` `GetVersionNumber` 는 해당 함수에 대해 버전 1, 2 또는 4를 반환할 수 있지만 버전 3은 반환할 수 없습니다. 이 함수에는 버전 3이 포함 되지 않습니다.  
  
 버전 번호는 각 모듈에 대해 개별적으로 추적 됩니다. 따라서 모듈 1에서 4 개의 편집을 수행 하 고 모듈 2에서는 지정 하지 않을 경우 모듈 1에서 다음 편집은 모듈 1의 모든 편집 된 함수에 버전 번호 6을 할당 합니다. 동일한 편집이 모듈 2를 터치 하는 경우 모듈 2의 함수는 버전 번호 2를 가져옵니다.  
  
 메서드에서 얻은 버전 번호는 `GetVersionNumber` [ICorDebugFunction:: GetCurrentVersionNumber](icordebugfunction-getcurrentversionnumber-method.md)에서 가져온 버전 보다 낮을 수 있습니다.  
  
 [ICorDebugCode:: GetVersionNumber](icordebugcode-getversionnumber-method.md) 메서드는와 동일한 작업을 수행 합니다 `ICorDebugFunction2::GetVersionNumber` .  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
