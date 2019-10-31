---
title: ICorDebugChain::GetActiveFrame 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetActiveFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetActiveFrame
helpviewer_keywords:
- ICorDebugChain::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 36887017-670b-4f21-b406-8fab956f84a3
topic_type:
- apiref
ms.openlocfilehash: 03cb1556ee971124ed4c591f38d9f892fc7df7b0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192152"
---
# <a name="icordebugchaingetactiveframe-method"></a>ICorDebugChain::GetActiveFrame 메서드
체인의 활성 (가장 최근) 프레임을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `ppFrame`  
 제한이 체인의 활성 (가장 최근) 프레임을 나타내는 ICorDebugFrame 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>주의  
 관리 되는 스택 프레임을 사용할 수 없는 경우 `ppFrame` null로 설정 됩니다.  
  
 활성 프레임을 사용할 수 없는 경우 호출이 성공 하 고 `ppFrame` null이 됩니다. CHAIN_ENTER_UNMANAGED으로 인해 시작 된 체인에 대해 활성 프레임을 사용할 수 없으며 CHAIN_CLASS_INIT로 인해 시작 된 일부 체인에 대해 활성 프레임을 사용할 수 없습니다. CorDebugChainReason 열거를 참조 하세요.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
