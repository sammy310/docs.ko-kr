---
title: 'Icordebugmemorybuffer:: Getstartaddress 메서드'
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 58649a0fc12ce63a1307af5d831dbf5e0d5a776a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61916528"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a>Icordebugmemorybuffer:: Getstartaddress 메서드
메모리 버퍼의 시작 주소를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `address`  
 [out] 메모리 버퍼의 시작 주소에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  
  
> [!WARNING]
>  이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>참고자료

- [ICorDebugMemoryBuffer 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
