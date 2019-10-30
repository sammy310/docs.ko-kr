---
title: ICorDebugThread::CreateStepper 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread.CreateStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::CreateStepper
helpviewer_keywords:
- ICorDebugThread::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 4657443f-dd12-431b-a648-175c23f13c83
topic_type:
- apiref
ms.openlocfilehash: d1b058aef66ed32c2cadcc3cfd72320dd8eb7729
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133589"
---
# <a name="icordebugthreadcreatestepper-method"></a>ICorDebugThread::CreateStepper 메서드
이 ICorDebugThread의 활성 프레임을 단계별로 실행할 수 있도록 하는 ICorDebugStepper 개체를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `ppStepper`  
 제한이 이 스레드의 활성 프레임을 단계별로 실행할 수 있도록 하는 `ICorDebugStepper` 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>주의  
 활성 프레임은 비관리 코드 일 수 있습니다.  
  
 실제 단계별 실행을 수행 하려면 `ICorDebugStepper` 인터페이스를 사용 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
