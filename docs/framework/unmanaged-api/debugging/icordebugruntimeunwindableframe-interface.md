---
description: '자세히 알아보기: ICorDebugRuntimeUnwindableFrame 인터페이스'
title: ICorDebugRuntimeUnwindableFrame 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugUnwindableFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnwindableFrame
helpviewer_keywords:
- ICorDebugUnwindableFrame interface [.NET Framework debugging]
ms.assetid: cd6a3982-6ed3-4909-808d-a66055e813e0
topic_type:
- apiref
ms.openlocfilehash: e83ede8265a400b30f2202115bf47aed6ea43e5e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717812"
---
# <a name="icordebugruntimeunwindableframe-interface"></a>ICorDebugRuntimeUnwindableFrame 인터페이스

프레임을 해제하는 데 CLR(공용 언어 런타임)을 필요로 하는 관리되지 않는 메서드에 대한 지원을 제공합니다.  
  
## <a name="remarks"></a>설명  

 `ICorDebugRuntimeUnwindableFrame` 는 ICorDebugFrame 인터페이스의 특수 버전입니다. 런타임이 현재 스택의 프레임을 해제 해야 하는 관리 되지 않는 메서드에서 사용 됩니다. 기존 해제 규칙은 JIT 컴파일된 코드를 사용 하지 않기 때문에 작동 하지 않습니다. 디버거는 unwindable 프레임을 볼 때 [ICorDebugStackWalk:: Next](icordebugstackwalk-next-method.md) 메서드를 사용 하 여 해제 해야 하지만 검사를 수행 해야 합니다. 디버거는를 받을 때 `ICorDebugRuntimeUnwindableFrame` [ICorDebugStackWalk:: getcontext](icordebugstackwalk-getcontext-method.md) 메서드를 호출 하 여 프레임의 컨텍스트를 검색할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [디버깅 인터페이스](debugging-interfaces.md)
- [디버깅](index.md)
