---
title: ICorDebugChain::GetStackRange 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetStackRange
helpviewer_keywords:
- ICorDebugChain::GetStackRange method [.NET Framework debugging]
- GetStackRange method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 554284e7-3f6c-4d40-8da5-1c9317fbd484
topic_type:
- apiref
ms.openlocfilehash: d9430c5a1f37a0507b383ea5437f7d7fed706c43
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123858"
---
# <a name="icordebugchaingetstackrange-method"></a>ICorDebugChain::GetStackRange 메서드
이 체인의 스택 세그먼트에 대 한 주소 범위를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pStart`  
 제한이 스택 세그먼트의 시작 주소인 `CORDB_ADDRESS` 값에 대 한 포인터입니다.  
  
 `pEnd`  
 제한이 스택 세그먼트의 끝 주소인 `CORDB_ADDRESS` 값에 대 한 포인터입니다.  
  
## <a name="remarks"></a>주의  
 숫자 범위는 스택 프레임 위치를 비교 하는 경우에만 의미가 있습니다. 실제로 스택에 저장 되는 항목에 대 한 가정을 만들 수는 없습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
