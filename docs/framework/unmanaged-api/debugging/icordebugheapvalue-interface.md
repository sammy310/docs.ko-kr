---
title: ICorDebugHeapValue 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue
helpviewer_keywords:
- ICorDebugHeapValue interface [.NET Framework debugging]
ms.assetid: 1bca66db-0359-4ae8-846e-e35f7e547e8b
topic_type:
- apiref
ms.openlocfilehash: fa31b8a6cc96935319e9bef3e561790b65e33a87
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777586"
---
# <a name="icordebugheapvalue-interface"></a>ICorDebugHeapValue 인터페이스

CLR (공용 언어 런타임) 가비지 수집기에 의해 수집 된 개체를 나타내는 "ICorDebugValue"의 서브 클래스입니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[CreateRelocBreakpoint 메서드](icordebugheapvalue-createrelocbreakpoint-method.md)|구현되지 않았습니다.|  
|[IsValid 메서드](icordebugheapvalue-isvalid-method.md)|이 `ICorDebugHeapValue` 나타내는 개체가 유효한 지 또는 가비지 수집기에 의해 회수 되었는지 여부를 나타내는 값을 가져옵니다. 이 메서드는 .NET Framework 버전 2.0에서 더 이상 사용 되지 않습니다.|  
  
## <a name="remarks"></a>주의  
  
> [!NOTE]
> 이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 인터페이스](debugging-interfaces.md)
