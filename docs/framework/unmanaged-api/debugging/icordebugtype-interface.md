---
title: ICorDebugType 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType
helpviewer_keywords:
- ICorDebugType interface [.NET Framework debugging]
ms.assetid: 94e02e31-67ea-4b00-8148-a46740a4571d
topic_type:
- apiref
ms.openlocfilehash: 8210e67f4bdd615ff65d9bd3474043fc45fd8883
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791255"
---
# <a name="icordebugtype-interface"></a>ICorDebugType 인터페이스
기본 또는 복합 형식 (즉, 사용자 정의)을 나타냅니다. 형식이 제네릭이면 `ICorDebugType`는 인스턴스화된 제네릭 형식을 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[EnumerateTypeParameters 메서드](icordebugtype-enumeratetypeparameters-method.md)|이 `ICorDebugType`에서 참조 하는 클래스의 제네릭 <xref:System.Type> 매개 변수를 참조 하는 ICorDebugTypeEnum에 대 한 인터페이스 포인터를 가져옵니다.|  
|[GetBase 메서드](icordebugtype-getbase-method.md)|이 `ICorDebugType`참조 하는 클래스의 기본 클래스 (있는 경우)를 참조 하는 `ICorDebugType`에 대 한 인터페이스 포인터를 가져옵니다.|  
|[GetClass 메서드](icordebugtype-getclass-method.md)|이 `ICorDebugType`의 형식화 된 생성자를 참조 하는 ICorDebugClass에 대 한 인터페이스 포인터를 가져옵니다.|  
|[GetFirstTypeParameter 메서드](icordebugtype-getfirsttypeparameter-method.md)|이 `ICorDebugType`에서 참조 하는 클래스의 생성자에 대 한 첫 번째 제네릭 <xref:System.Type> 매개 변수를 참조 하는 `ICorDebugType`에 대 한 인터페이스 포인터를 가져옵니다.|  
|[GetRank 메서드](icordebugtype-getrank-method.md)|배열 형식의 차원 수를 가져옵니다.|  
|[GetStaticFieldValue 메서드](icordebugtype-getstaticfieldvalue-method.md)|지정 된 스택 프레임에서 지정 된 필드 토큰이 참조 하는 정적 필드의 값을 포함 하는 ICorDebugValue에 대 한 인터페이스 포인터를 가져옵니다.|  
|[GetType 메서드](icordebugtype-gettype-method.md)|이 `ICorDebugType`에서 참조 하 <xref:System.Type> 공용 언어 런타임의 네이티브 형식을 설명 하는 CorElementType 값을 가져옵니다.|  
  
## <a name="remarks"></a>주의  
 형식이 제네릭이 면 `ICorDebugClass` 인스턴스화되지 않은 형식을 나타냅니다. `ICorDebugType` 인터페이스는 인스턴스화된 제네릭 형식을 나타냅니다. 예를 들어 Hashtable\<K, V >는 `ICorDebugClass`으로 표시 되는 반면 Hashtable\<Int32, 문자열 >는 `ICorDebugType`로 표시 됩니다.  
  
 제네릭이 아닌 형식은 `ICorDebugClass`와 `ICorDebugType`둘 다로 표시 됩니다. 후자 인터페이스는 형식 인스턴스화를 처리 하기 위해 .NET Framework 버전 2.0에서 도입 되었습니다.  
  
> [!NOTE]
> 이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 인터페이스](debugging-interfaces.md)
