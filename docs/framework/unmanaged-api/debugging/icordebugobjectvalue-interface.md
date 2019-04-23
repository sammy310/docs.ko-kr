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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d0ac91681313b60ebfcaf725dcc2e0d6547e3c1b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59222616"
---
# <a name="icordebugobjectvalue-interface"></a>ICorDebugObjectValue 인터페이스

개체를 포함 하는 값을 나타내는 "ICorDebugValue"의 하위 클래스.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetClass 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md)|CLR (공용 언어 런타임)에 인터페이스 포인터를 가져옵니다 <xref:System.Type> 개체의이 `ICorDebugObjectValue` 참조 합니다.|  
|[GetContext 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getcontext-method.md)|구현되지 않았습니다.|  
|[GetFieldValue 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getfieldvalue-method.md)|한 인터페이스 포인터를 가져옵니다는 [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md) 지정된 된 클래스의 지정된 된 필드의 값을 나타내는입니다.|  
|[GetManagedCopy 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getmanagedcopy-method.md)|사용되지 않습니다. 이 메서드를 호출 하지 마세요.|  
|[GetVirtualMethod 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getvirtualmethod-method.md)|구현되지 않았습니다.|  
|[IsValueClass 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-isvalueclass-method.md)|이 개체를 참조 하는지 여부를 나타내는 값을 가져옵니다 `ICorDebugObjectValue` 값 형식입니다.|  
|[SetFromManagedCopy 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-setfrommanagedcopy-method.md)|사용되지 않습니다. 이 메서드를 호출 하지 마세요.|  
  
## <a name="remarks"></a>설명  
 `ICorDebugObjectValue` 디버깅 중인 프로세스가 계속 될 때까지 유효 합니다.  
  
> [!NOTE]
>  이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
