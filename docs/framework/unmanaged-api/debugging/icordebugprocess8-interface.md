---
description: '자세히 알아보기: ICorDebugProcess8 인터페이스'
title: ICorDebugProcess8 인터페이스
ms.date: 03/30/2017
ms.assetid: 7ab1a70f-ec11-46ff-8869-cd8ca679cc51
ms.openlocfilehash: d858470216cfe64c60902836e552f750f4b2d5ec
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99691291"
---
# <a name="icordebugprocess8-interface"></a>ICorDebugProcess8 인터페이스

[.NET Framework 4.6 이상 버전에서 지원 됨]  
  
 ICorDebugProcess 인터페이스를 논리적으로 확장 하 여 특정 형식의 [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) 예외 콜백을 사용 하거나 사용 하지 않도록 설정 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[EnableExceptionCallbacksOutsideOfMyCode 메서드](icordebugprocess8-enableexceptioncallbacksoutsideofmycode-method.md)|특정 형식의 [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) 예외 콜백을 사용 하거나 사용 하지 않도록 설정 합니다.|  
  
## <a name="remarks"></a>설명  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [디버깅 인터페이스](debugging-interfaces.md)
- [디버깅](index.md)
