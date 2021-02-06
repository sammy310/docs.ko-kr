---
description: '자세히 알아보기: ICorDebugModule2 인터페이스'
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
ms.openlocfilehash: 28de1f0d3411218ac92991d4fceda0612c8199bf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659935"
---
# <a name="icordebugmodule2-interface"></a>ICorDebugModule2 인터페이스

ICorDebugModule 인터페이스에 대 한 논리적 확장으로 사용 됩니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[ApplyChanges 메서드](icordebugmodule2-applychanges-method.md)|메타 데이터의 변경 내용과 MSIL (Microsoft 중간 언어) 코드의 변경 내용을 실행 중인 프로세스에 적용 합니다.|  
|[GetJITCompilerFlags 메서드](icordebugmodule2-getjitcompilerflags-method.md)|이에 대 한 JIT (just-in-time) 컴파일을 제어 하는 플래그를 가져옵니다 `ICorDebugModule2` .|  
|[ResolveAssembly 메서드](icordebugmodule2-resolveassembly-method.md)|지정 된 메타 데이터 토큰에서 참조 하는 어셈블리를 확인 합니다.|  
|[SetJITCompilerFlags 메서드](icordebugmodule2-setjitcompilerflags-method.md)|이에 대 한 JIT 컴파일을 제어 하는 플래그를 설정 합니다 `ICorDebugModule2` .|  
|[SetJMCStatus 메서드](icordebugmodule2-setjmcstatus-method.md)|이에 있는 모든 클래스의 모든 메서드에 대 한 내 코드만 (JMC) 상태를 지정 된 값으로 설정 합니다 `ICorDebugModule2` . 단, `pTokens` 배열의 값은 반대 값으로 설정 됩니다.|  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
> 이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [디버깅 인터페이스](debugging-interfaces.md)
