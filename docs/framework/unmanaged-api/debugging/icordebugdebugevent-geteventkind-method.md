---
description: '자세히 알아보기: ICorDebugDebugEvent:: GetEventKind 메서드'
title: ICorDebugDebugEvent::GetEventKind 메서드
ms.date: 03/30/2017
ms.assetid: c37aaceb-c948-46bd-a943-08be4cbb76f4
ms.openlocfilehash: 9e15eb82195fae8aa3797ea47cb04d0bb407d2ad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764322"
---
# <a name="icordebugdebugeventgeteventkind-method"></a>ICorDebugDebugEvent::GetEventKind 메서드

이 `ICorDebugDebugEvent` 개체가 나타내는 이벤트의 종류를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetEventKind(  
    [out]CorDebugDebugEventKind *pDebugEventKind  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 pDebugEventKind  
 이벤트 유형을 나타내는 [Cordebugdebugeventkind](cordebugdebugeventkind-enumeration.md) 열거형 멤버에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 `pDebugEventKind`의 값에 따라 `QueryInterface`를 호출하여 추가 데이터를 포함하는 보다 정확한 디버그 이벤트 인터페이스를 가져올 수 있습니다.  
  
> [!NOTE]
> 이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorDebugDebugEvent 인터페이스](icordebugdebugevent-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
