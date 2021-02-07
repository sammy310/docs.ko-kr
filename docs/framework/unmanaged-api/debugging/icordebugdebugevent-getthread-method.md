---
description: '자세히 알아보기: ICorDebugDebugEvent:: GetThread 메서드'
title: ICorDebugDebugEvent::GetThread 메서드
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
ms.openlocfilehash: 1d476603572f31882f481d414e483c6712f1b5fc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710415"
---
# <a name="icordebugdebugeventgetthread-method"></a>ICorDebugDebugEvent::GetThread 메서드

이벤트가 발생한 스레드를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 ppThread  
 [out] 이벤트가 발생한 스레드를 나타내는 ICorDebugThread 개체의 주소에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  
  
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
