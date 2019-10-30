---
title: ICorDebugModule2 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugModule2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2
helpviewer_keywords:
- ICorDebugModule2 interface [.NET Framework debugging]
ms.assetid: 0847e64f-fdbe-4c96-8168-da20fdc84d80
topic_type:
- apiref
ms.openlocfilehash: a3a1b658f4ab05c7029de907882fe5ab2513ccd8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127882"
---
# <a name="icordebugmodule2-interface"></a>ICorDebugModule2 인터페이스

ICorDebugModule 인터페이스에 대 한 논리적 확장으로 사용 됩니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[ApplyChanges 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md)|메타 데이터의 변경 내용과 MSIL (Microsoft 중간 언어) 코드의 변경 내용을 실행 중인 프로세스에 적용 합니다.|  
|[GetJITCompilerFlags 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-getjitcompilerflags-method.md)|이 `ICorDebugModule2`에 대 한 JIT (just-in-time) 컴파일을 제어 하는 플래그를 가져옵니다.|  
|[ResolveAssembly 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-resolveassembly-method.md)|지정 된 메타 데이터 토큰에서 참조 하는 어셈블리를 확인 합니다.|  
|[SetJITCompilerFlags 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md)|이 `ICorDebugModule2`에 대 한 JIT 컴파일을 제어 하는 플래그를 설정 합니다.|  
|[SetJMCStatus 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjmcstatus-method.md)|이 `ICorDebugModule2`에 있는 모든 클래스의 모든 메서드에 대 한 내 코드만 (JMC) 상태를 지정 된 값으로 설정 합니다. 단,이 값은 `pTokens` 배열의 값이 반대 값으로 설정 됩니다.|  
  
## <a name="remarks"></a>주의  
  
> [!NOTE]
> 이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
