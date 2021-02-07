---
description: '자세히 알아보기: ICorDebugChain:: GetActiveFrame 메서드'
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
ms.openlocfilehash: d46906d9d6c671880d9446d889cdf9f83f3b4366
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661425"
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
  
## <a name="remarks"></a>설명  

 관리 되는 스택 프레임을 사용할 수 없는 경우 `ppFrame` 은 null로 설정 됩니다.  
  
 활성 프레임을 사용할 수 없는 경우 호출은 성공 하 고 `ppFrame` null이 됩니다. CHAIN_ENTER_UNMANAGED로 인해 시작 된 체인에 대해 활성 프레임을 사용할 수 없으며, CHAIN_CLASS_INIT으로 인해 시작 된 일부 체인에 대해 활성 프레임을 사용할 수 없습니다. CorDebugChainReason 열거를 참조 하세요.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
