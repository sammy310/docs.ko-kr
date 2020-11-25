---
title: ICorDebugObjectValue 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue
helpviewer_keywords:
- ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 937de6a0-6fbf-4ddc-80ea-a6217b73e62b
topic_type:
- apiref
ms.openlocfilehash: 2a5a618491bf2c624669728d97a690cca315bff8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724678"
---
# <a name="icordebugobjectvalue-interface"></a>ICorDebugObjectValue 인터페이스

개체를 포함 하는 값을 나타내는 "ICorDebugValue"의 서브 클래스입니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetClass 메서드](icordebugobjectvalue-getclass-method.md)|<xref:System.Type>이가 참조 하는 개체의 CLR (공용 언어 런타임)에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugObjectValue` .|  
|[GetContext 메서드](icordebugobjectvalue-getcontext-method.md)|구현되지 않았습니다.|  
|[GetFieldValue 메서드](icordebugobjectvalue-getfieldvalue-method.md)|지정 된 클래스의 지정 된 필드 값을 나타내는 [ICorDebugValue](icordebugvalue-interface.md) 에 대 한 인터페이스 포인터를 가져옵니다.|  
|[GetManagedCopy 메서드](icordebugobjectvalue-getmanagedcopy-method.md)|사용되지 않습니다. 이 메서드를 호출 하지 마십시오.|  
|[GetVirtualMethod 메서드](icordebugobjectvalue-getvirtualmethod-method.md)|구현되지 않았습니다.|  
|[IsValueClass 메서드](icordebugobjectvalue-isvalueclass-method.md)|이에서 참조 하는 개체가 값 형식 인지 여부를 나타내는 값을 가져옵니다 `ICorDebugObjectValue` .|  
|[SetFromManagedCopy 메서드](icordebugobjectvalue-setfrommanagedcopy-method.md)|사용되지 않습니다. 이 메서드를 호출 하지 마십시오.|  
  
## <a name="remarks"></a>설명  

 는 `ICorDebugObjectValue` 디버그 중인 프로세스가 계속 될 때까지 유효한 상태로 유지 됩니다.  
  
> [!NOTE]
> 이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 인터페이스](debugging-interfaces.md)
