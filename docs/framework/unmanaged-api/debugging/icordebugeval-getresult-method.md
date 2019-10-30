---
title: ICorDebugEval::GetResult 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval.GetResult
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::GetResult
helpviewer_keywords:
- ICorDebugEval::GetResult method [.NET Framework debugging]
- GetResult method [.NET Framework debugging]
ms.assetid: 50dbb9af-58a1-41f4-b56d-3da20011884f
topic_type:
- apiref
ms.openlocfilehash: 52bfe669d3b078657916554255a11cecfc07d484
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73085082"
---
# <a name="icordebugevalgetresult-method"></a>ICorDebugEval::GetResult 메서드
이 계산의 결과를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetResult (  
    [out] ICorDebugValue    **ppResult  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `ppResult`  
 제한이 평가가 정상적으로 완료 되는 경우이 계산의 결과를 나타내는 ICorDebugValue 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>주의  
 `GetResult` 메서드는 평가가 완료 된 후에만 유효 합니다.  
  
 평가가 정상적으로 완료 되는 경우 `ppResult` 결과를 지정 합니다. 예외로 인해 종료 되 면 예외가 throw 됩니다. 새 개체에 대 한 평가 인 경우 결과는 새 개체에 대 한 참조입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
