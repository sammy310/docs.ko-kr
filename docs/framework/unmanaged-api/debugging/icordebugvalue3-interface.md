---
title: ICorDebugValue3 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugValue3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue3
helpviewer_keywords:
- ICorDebugValue3 interface [.NET Framework debugging]
ms.assetid: 7d5385d3-f4a5-47c4-8478-a3513b5e9406
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 300d2263c076c9028340863e2f7a3fa27a36ef9d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993735"
---
# <a name="icordebugvalue3-interface"></a>ICorDebugValue3 인터페이스
2GB 보다 큰 배열 지원 하기 위해 "ICorDebugValue" 및 "ICorDebugValue2" 인터페이스를 확장 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetSize64 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)|이 바이트 단위로 크기를 가져옵니다 `ICorDebugValue3` 개체입니다.|  
  
## <a name="remarks"></a>설명  
 합니다 [icordebugvalue:: Getsize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) 메서드 범위 개체 크기를 0에서 2,147,483,647 바이트를 반환 합니다. 에 [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], 배열의 크기는 2GB를 초과할 수 있습니다. `ICorDebugValue3` 인터페이스를 사용 하면 이러한 배열 크기를 확인할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
