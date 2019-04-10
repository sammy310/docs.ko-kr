---
title: ICorDebugReferenceValue 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue
helpviewer_keywords:
- ICorDebugReferenceValue interface [.NET Framework debugging]
ms.assetid: 2040e2be-119a-4cfb-ae52-b0b6f052665c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d6575acfb1f75cbc8e3d59ddca5fea0953274cf2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59206462"
---
# <a name="icordebugreferencevalue-interface"></a>ICorDebugReferenceValue 인터페이스
개체에 대 한 참조는 값을 관리 하는 메서드를 제공 합니다. (즉,이 메서드는 대 한 포인터를 관리 하는 합니다.) 이 인터페이스는 "ICorDebugValue"를 구현합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Dereference 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereference-method.md)|참조 되는 개체를 가져옵니다.|  
|[DereferenceStrong 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereferencestrong-method.md)|구현되지 않았습니다. 이 메서드를 호출 하지 마세요.|  
|[GetValue 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-getvalue-method.md)|참조 된 개체의 현재 메모리 주소를 가져옵니다.|  
|[IsNull 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-isnull-method.md)|나타내는 값을 가져옵니다 여부를이 `ICorDebugReferenceValue` null 값인 경우,이 경우에 `ICorDebugReferenceValue` 개체를 가리키지 않습니다.|  
|[SetValue 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-setvalue-method.md)|현재 메모리 주소를 설정합니다. 이 메서드가이 설정, `ICorDebugReferenceValue` 개체를 가리키도록 합니다.|  
  
## <a name="remarks"></a>설명  
 디버깅된 된 프로세스는 계속 하는 경우는 CLR (공용 언어 런타임) 개체의 가비지 컬렉션을 수행할 수 있습니다. 가비지 수집이 메모리에 개체를 이동할 수 있습니다. `ICorDebugReferenceValue` 됩니다 하나 보이도록 가비지 수집을 사용 하 여 가비지 컬렉션 후 해당 정보를 업데이트 하거나 가비지 컬렉션 전에 암시적으로 무효화 됩니다.  
  
 `ICorDebugReferenceValue` 디버깅된 된 프로세스 계속 된 후 개체가 암시적으로 무효화 될 수 있습니다. 명시적으로 해제 되거나 표시 될 때까지 파생된 "ICorDebugHandleValue" 무효화 되지 않았습니다.  
  
> [!NOTE]
>  이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
