---
title: ICorDebugVariableSymbol 인터페이스
ms.date: 03/30/2017
ms.assetid: 0e58b85e-69bd-41ff-bedb-8cdc8be6a7a2
ms.openlocfilehash: 9d17bc92dcae9e906dfe18d7665fbf489d278234
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790868"
---
# <a name="icordebugvariablesymbol-interface"></a>ICorDebugVariableSymbol 인터페이스
변수에 대한 디버그 기호 정보를 검색합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetName 메서드](icordebugvariablesymbol-getname-method.md)|변수의 이름을 가져옵니다.|  
|[GetSize 메서드](icordebugvariablesymbol-getsize-method.md)|변수의 크기(바이트)를 가져옵니다.|  
|[GetSlotIndex 메서드](icordebugvariablesymbol-getslotindex-method.md)|지역 변수의 관리되는 슬롯 인덱스를 가져옵니다.|  
|[GetValue 메서드](icordebugvariablesymbol-getvalue-method.md)|변수의 값을 바이트 배열로 가져옵니다.|  
|[SetValue 메서드](icordebugvariablesymbol-setvalue-method.md)|바이트 배열의 값을 변수에 할당합니다.|  
  
## <a name="remarks"></a>주의  
  
> [!NOTE]
> 이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다. .NET 네이티브 외부의 ICorDebug 시나리오에 대해 이 인터페이스를 구현하는 경우 공용 언어 런타임에서 이 인터페이스를 무시합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 인터페이스](debugging-interfaces.md)
- [디버깅](index.md)
