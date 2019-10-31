---
title: ICorDebugChain::GetCallee 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetCallee
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetCallee method
helpviewer_keywords:
- ICorDebugChain::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 19560c79-abdc-4bdf-a5fe-eb362a59edc0
topic_type:
- apiref
ms.openlocfilehash: 5d28af09faae84b0482d438ae33f593f250490c1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73196333"
---
# <a name="icordebugchaingetcallee-method"></a>ICorDebugChain::GetCallee 메서드
이 체인에 의해 호출 된 체인을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetCallee (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `ppChain`  
 제한이 호출 된 체인을 나타내는 ICorDebugChain 개체의 주소에 대 한 포인터입니다. 이 체인이 현재 실행 중인 경우 (즉,이 체인이 반환 될 호출 된 체인을 기다리지 않는 경우) `ppChain` null이 됩니다.  
  
## <a name="remarks"></a>주의  
 이 체인은 실행을 다시 시작 하기 전에 호출 된 체인이 반환 될 때까지 대기 합니다. 호출 된 체인은 크로스 스레드 마샬링된 호출의 경우 다른 스레드에 있을 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
