---
title: ICorDebugDebugEvent::GetThread 메서드
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 103768918f67ca695a47c52b9cd97f24fb8d46ce
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59081582"
---
# <a name="icordebugdebugeventgetthread-method"></a>ICorDebugDebugEvent::GetThread 메서드
이벤트가 발생한 스레드를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 ppThread  
 [out] 이벤트가 발생 한 스레드를 나타내는 ICorDebugThread 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
>  이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>참고자료

- [ICorDebugDebugEvent 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)
- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
