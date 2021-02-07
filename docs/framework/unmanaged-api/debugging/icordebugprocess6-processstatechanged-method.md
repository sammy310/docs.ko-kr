---
description: ICorDebugProcess6::P rocessStateChanged 메서드에 대해 자세히 알아보세요.
title: ICorDebugProcess6::ProcessStateChanged 메서드
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
ms.openlocfilehash: 8060c29598adf5d4bbe7bffb4cd6611ee19a2669
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99691369"
---
# <a name="icordebugprocess6processstatechanged-method"></a>ICorDebugProcess6::ProcessStateChanged 메서드

프로세스가 실행 중임을 [ICorDebug](icordebug-interface.md) 에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
## <a name="parameters"></a>매개 변수  

 `change`  
 진행 [ProcessStateChanged](icordebugprocess6-processstatechanged-method.md) 열거형의 멤버  
  
## <a name="remarks"></a>설명  

 디버거는이 메서드를 호출 하 여 프로세스가 실행 중임을 [ICorDebug](icordebug-interface.md) 에 알립니다.  
  
> [!NOTE]
> 이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorDebugProcess6 인터페이스](icordebugprocess6-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
