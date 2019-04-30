---
title: ICorDebugEval2 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugEval2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2
helpviewer_keywords:
- ICorDebugEval2 interface [.NET Framework debugging]
ms.assetid: fce34531-2687-406d-9131-d6ad94f2ce0e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3767368c9da8c97cd081787c0945a15552a1da46
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995971"
---
# <a name="icordebugeval2-interface"></a>ICorDebugEval2 인터페이스

확장 "ICorDebugEval" 제네릭 형식에 대 한 지원을 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[CallParameterizedFunction 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)|지정 된 "ICorDebugFunction"를 해당 생성자 형식 매개 변수 또는 형식 매개 변수 자체 들 형식 안에 중첩 될 수 있습니다는에 대 한 호출을 설정 합니다.|  
|[CreateValueForType 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)|초기 값이 null 또는 0을 사용 하 여 지정 된 형식의 새 "ICorDebugValue"에 대 한 포인터를 가져옵니다.|  
|[NewParameterizedArray 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md)|지정 된 요소 형식 및 차원에는 새 배열을 할당합니다.|  
|[NewParameterizedObject 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)|새 매개 변수가 있는 형식 개체를 인스턴스화하고 개체의 생성자 메서드를 호출 합니다.|  
|[NewParameterizedObjectNoConstructor 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)|Constructor 메서드를 호출 하려고 하지 않고 지정된 된 클래스의 새 매개 변수가 있는 형식 개체를 인스턴스화하십시오|  
|[NewStringWithLength 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newstringwithlength-method.md)|지정된 된 콘텐츠를 사용 하 여 지정 된 길이의 새 문자열을 만듭니다.|  
|[RudeAbort 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-rudeabort-method.md)|계산 중단이 `ICorDebugEval2` 현재 수행 중입니다.|  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
>  이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
