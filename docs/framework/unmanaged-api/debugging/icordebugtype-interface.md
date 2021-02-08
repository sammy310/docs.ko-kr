---
description: '자세히 알아보기: ICorDebugType 인터페이스'
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
ms.openlocfilehash: 4cd668263906ef21e1bb665795425ca3a239c2bd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800892"
---
# <a name="icordebugtype-interface"></a>ICorDebugType 인터페이스

기본 또는 복합 형식 (즉, 사용자 정의)을 나타냅니다. 형식이 제네릭이면 `ICorDebugType`는 인스턴스화된 제네릭 형식을 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[EnumerateTypeParameters 메서드](icordebugtype-enumeratetypeparameters-method.md)|<xref:System.Type>이에서 참조 하는 클래스의 제네릭 매개 변수를 참조 하는 ICorDebugTypeEnum에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugType` .|  
|[GetBase 메서드](icordebugtype-getbase-method.md)|`ICorDebugType`이가 참조 하는 클래스의 기본 클래스 (있는 경우)를 참조 하는에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugType` .|  
|[GetClass 메서드](icordebugtype-getclass-method.md)|이의 형식화 된 생성자를 참조 하는 ICorDebugClass에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugType` .|  
|[GetFirstTypeParameter 메서드](icordebugtype-getfirsttypeparameter-method.md)|`ICorDebugType` <xref:System.Type> 이에서 참조 하는 클래스의 생성자에 대 한 첫 번째 제네릭 매개 변수를 참조 하는에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugType` .|  
|[GetRank 메서드](icordebugtype-getrank-method.md)|배열 형식의 차원 수를 가져옵니다.|  
|[GetStaticFieldValue 메서드](icordebugtype-getstaticfieldvalue-method.md)|지정 된 스택 프레임에서 지정 된 필드 토큰이 참조 하는 정적 필드의 값을 포함 하는 ICorDebugValue에 대 한 인터페이스 포인터를 가져옵니다.|  
|[GetType 메서드](icordebugtype-gettype-method.md)|이에서 참조 하는 공용 언어 런타임의 네이티브 형식을 설명 하는 CorElementType 값을 가져옵니다 <xref:System.Type> `ICorDebugType` .|  
  
## <a name="remarks"></a>설명  

 형식이 제네릭인 경우는 인스턴스화되지 않은 `ICorDebugClass` 형식을 나타냅니다. `ICorDebugType`인터페이스는 인스턴스화된 제네릭 형식을 나타냅니다. 예를 들어 해시 테이블은로 \<K, V> 표현 되는 반면 hashtable은로 표현 됩니다 `ICorDebugClass` \<Int32, String> `ICorDebugType` .  
  
 제네릭이 아닌 형식은 및로 표시 됩니다 `ICorDebugClass` `ICorDebugType` . 후자 인터페이스는 형식 인스턴스화를 처리 하기 위해 .NET Framework 버전 2.0에서 도입 되었습니다.  
  
> [!NOTE]
> 이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [디버깅 인터페이스](debugging-interfaces.md)
