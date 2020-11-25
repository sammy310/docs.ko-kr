---
title: ICorDebugILFrame 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame
helpviewer_keywords:
- ICorDebugILFrame interface [.NET Framework debugging]
ms.assetid: d5cf5056-da4d-4629-914d-afe42a5393df
topic_type:
- apiref
ms.openlocfilehash: 4f34fdf9a0eeb47e027cc874afee5bd04f5bd9bc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712393"
---
# <a name="icordebugilframe-interface"></a>ICorDebugILFrame 인터페이스

MSIL (Microsoft 중간 언어) 코드의 스택 프레임을 나타냅니다. 이 인터페이스는 ICorDebugFrame 인터페이스의 하위 클래스입니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[CanSetIP 메서드](icordebugilframe-cansetip-method.md)|지정 된 오프셋 위치에 명령 포인터를 설정 하는 것이 안전한 지 여부를 나타내는 값을 가져옵니다.|  
|[EnumerateArguments 메서드](icordebugilframe-enumeratearguments-method.md)|이 프레임의 인수에 대 한 열거자를 가져옵니다.|  
|[EnumerateLocalVariables 메서드](icordebugilframe-enumeratelocalvariables-method.md)|이 프레임의 지역 변수에 대 한 열거자를 가져옵니다.|  
|[GetArgument 메서드](icordebugilframe-getargument-method.md)|이 MSIL 스택 프레임에서 지정 된 인수의 값을 가져옵니다.|  
|[GetIP 메서드](icordebugilframe-getip-method.md)|명령 포인터의 값과 명령 포인터의 값을 가져오는 방법을 설명 하는 비트 조합 값을 가져옵니다.|  
|[GetLocalVariable 메서드](icordebugilframe-getlocalvariable-method.md)|이 MSIL 스택 프레임에서 지정 된 지역 변수의 값을 가져옵니다.|  
|[GetStackDepth 메서드](icordebugilframe-getstackdepth-method.md)|구현되지 않았습니다.|  
|[GetStackValue 메서드](icordebugilframe-getstackvalue-method.md)|구현되지 않았습니다.|  
|[SetIP 메서드](icordebugilframe-setip-method.md)|MSIL 코드에서 지정 된 오프셋 위치에 대 한 명령 포인터를 설정 합니다.|  
  
## <a name="remarks"></a>설명  

 `ICorDebugILFrame`인터페이스는 특수 한 ICorDebugFrame 인터페이스입니다. MSIL 코드 프레임 또는 JIT (just-in-time) 컴파일된 프레임에 사용 됩니다. JIT 컴파일된 프레임은 `ICorDebugILFrame` 인터페이스와 ICorDebugNativeFrame 인터페이스를 둘 다 구현 합니다.  
  
> [!NOTE]
> 이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 인터페이스](debugging-interfaces.md)
