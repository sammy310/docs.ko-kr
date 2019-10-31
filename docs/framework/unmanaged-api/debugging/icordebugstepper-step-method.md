---
title: ICorDebugStepper::Step 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.Step
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::Step
helpviewer_keywords:
- Step method, ICorDebugStepper interface [.NET Framework debugging]
- ICorDebugStepper::Step method [.NET Framework debugging]
ms.assetid: 38c1940b-ada1-40ba-8295-4c0833744e1e
topic_type:
- apiref
ms.openlocfilehash: 43f86e704e4a52a702b8f563e3c613806eb061b5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137528"
---
# <a name="icordebugstepperstep-method"></a>ICorDebugStepper::Step 메서드
이 ICorDebugStepper는 해당 스레드를 포함 하는 스레드를 한 단계씩 실행 하 고, 필요에 따라 스레드 내에서 호출 되는 함수를 통해 단일 단계를 계속 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Step (  
    [in] BOOL   bStepIn  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `bStepIn`  
 진행 `true` 설정 하 여 스레드 내에서 호출 되는 함수를 한 단계씩 실행 합니다. 함수를 프로시저 단위로 실행 하려면 `false`로 설정 합니다.  
  
## <a name="remarks"></a>주의  
 공용 언어 런타임이이 스텝 퍼의 프레임에서 다음의 관리 되는 명령을 수행할 때 단계가 완료 됩니다. 관리 코드에 없는 스텝 퍼에서 `Step`를 호출 하는 경우 스레드는 다음 관리 코드 명령이 실행 될 때 단계가 완료 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
