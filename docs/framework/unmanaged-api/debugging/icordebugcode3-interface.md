---
title: ICorDebugCode3 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugCode3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode3
helpviewer_keywords:
- ICorDebugCode3 interface [.NET Framework debugging]
ms.assetid: 70f07c9e-0614-4bee-ac34-09fe6c51c5a9
topic_type:
- apiref
ms.openlocfilehash: f2f75c3c54c0fa2d55dc0179c05e4edea6e36738
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777821"
---
# <a name="icordebugcode3-interface"></a>ICorDebugCode3 인터페이스
관리 되는 반환 값에 대 한 정보를 제공 하기 위해 "ICorDebugCode" 및 "ICorDebugCode2"를 확장 하는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetReturnValueLiveOffset 메서드](icordebugcode3-getreturnvalueliveoffset-method.md)|지정 된 IL 오프셋의 경우 디버거가 함수에서 반환 값을 가져올 수 있도록 중단점이 배치 되어야 하는 네이티브 오프셋을 가져옵니다.|  
  
## <a name="remarks"></a>주의  
  
> [!NOTE]
> 이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugILFrame3 인터페이스](icordebugilframe3-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
