---
description: '자세히 알아보기: ICorDebugVirtualUnwinder:: Next 메서드'
title: ICorDebugVirtualUnwinder::Next 메서드
ms.date: 03/30/2017
ms.assetid: 790e0426-e5cd-49fd-a792-f8c8635d72fe
ms.openlocfilehash: b509e8e4fb24c66764999e67ba7e36299ce7f570
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790518"
---
# <a name="icordebugvirtualunwindernext-method"></a>ICorDebugVirtualUnwinder::Next 메서드

호출자의 컨텍스트로 이동합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Next();  
```  
  
## <a name="parameters"></a>매개 변수  

 없음  
  
## <a name="return-value"></a>Return Value  

 해제가 성공적으로 발생한 경우 `S_OK`이고, 더 이상 프레임이 없어 해제를 완료할 수 없는 경우 `CORDBG_S_AT_END_OF_STACK`입니다.  
  
 실패 HRESULT가 반환되면 ICorDebug API에서 `CORDBG_E_DATA_TARGET_ERROR`를 반환합니다.  
  
## <a name="remarks"></a>설명  

 궁극적으로 `Next` 호출에서 실패 HRESULT 또는 `CORDBG_S_AT_END_OF_STACK`이 반환되도록 스택 워크에서 정방향 진행 중인지 확인해야 합니다. `S_OK`무기한 반환 하면 무한 루프가 발생할 수 있습니다.  
  
> [!NOTE]
> 이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorDebugMemoryBuffer 인터페이스](icordebugmemorybuffer-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
