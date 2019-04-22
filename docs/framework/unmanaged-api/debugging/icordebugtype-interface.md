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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 74863af1096f8600b8095e593c1f3c820c512e9d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59166805"
---
# <a name="icordebugtype-interface"></a>ICorDebugType 인터페이스
형식을, 기본 또는 복합 (즉, 사용자 정의)를 나타냅니다. 형식이 제네릭이면 `ICorDebugType`는 인스턴스화된 제네릭 형식을 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[EnumerateTypeParameters 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-enumeratetypeparameters-method.md)|제네릭 참조 하는 ICorDebugTypeEnum에 대 한 인터페이스 포인터를 가져옵니다 <xref:System.Type> 이 참조 하는 클래스의 매개 변수 `ICorDebugType`합니다.|  
|[GetBase 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getbase-method.md)|한 인터페이스 포인터를 가져옵니다는 `ICorDebugType` 이 참조 하는 클래스의 기본 클래스를 참조 하는 `ICorDebugType`있는 경우.|  
|[GetClass 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)|이 형식의 생성자를 참조 하는 ICorDebugClass에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugType`합니다.|  
|[GetFirstTypeParameter 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getfirsttypeparameter-method.md)|한 인터페이스 포인터를 가져옵니다는 `ICorDebugType` 를 참조 하는 첫 번째 제네릭 <xref:System.Type> 이 참조 하는 클래스의 생성자에 대 한 매개 변수 `ICorDebugType`합니다.|  
|[GetRank 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getrank-method.md)|배열 형식의 차수를 가져옵니다.|  
|[GetStaticFieldValue 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md)|지정한 스택 프레임에서 토큰에 지정 된 필드에서 참조 하는 정적 필드의 값이 포함 된 ICorDebugValue 인터페이스 포인터를 가져옵니다.|  
|[GetType 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)|공용 언어 런타임의 네이티브 형식을 설명 하는 CorElementType 값을 가져옵니다 <xref:System.Type> 이 참조 `ICorDebugType`합니다.|  
  
## <a name="remarks"></a>설명  
 형식이 제네릭인 경우 `ICorDebugClass` 인스턴스화되지 않은 형식을 나타냅니다. `ICorDebugType` 인터페이스는 인스턴스화된 제네릭 형식을 나타냅니다. 예를 들어 Hashtable\<K, V >을 표시 `ICorDebugClass`반면 Hashtable\<Int32, String >을 표시 `ICorDebugType`합니다.  
  
 제네릭이 아닌 형식은 둘 다 표시 됩니다 `ICorDebugClass` 고 `ICorDebugType`입니다. 두 번째 인터페이스 형식 인스턴스화를 사용 하 여 처리 하는.NET Framework 버전 2.0에서에서 도입 되었습니다.  
  
> [!NOTE]
>  이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
