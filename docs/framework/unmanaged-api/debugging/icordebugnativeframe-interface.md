---
description: '자세히 알아보기: ICorDebugNativeFrame 인터페이스'
title: ICorDebugNativeFrame 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame
helpviewer_keywords:
- ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 04819c58-7246-4b32-befb-680cf1dbc436
topic_type:
- apiref
ms.openlocfilehash: e417184c9f1ca5136e1b4dba07820fd8242ae932
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729135"
---
# <a name="icordebugnativeframe-interface"></a>ICorDebugNativeFrame 인터페이스

네이티브 프레임에 사용 되는 ICorDebugFrame의 특수화 된 구현입니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[CanSetIP 메서드](icordebugnativeframe-cansetip-method.md)|네이티브 코드에서 지정 된 오프셋 위치에 대 한 명령 포인터를 설정 하는 것이 안전한 지 여부를 나타내는 값을 가져옵니다.|  
|[GetIP 메서드](icordebugnativeframe-getip-method.md)|네이티브 코드에 대 한 스택 프레임의 오프셋을 가져옵니다.|  
|[GetLocalDoubleRegisterValue 메서드](icordebugnativeframe-getlocaldoubleregistervalue-method.md)|네이티브 프레임의 두 메모리 레지스터에 저장 된 인수나 지역 변수의 값을 나타내는 ICorDebugValue에 대 한 포인터를 가져옵니다.|  
|[GetLocalMemoryRegisterValue 메서드](icordebugnativeframe-getlocalmemoryregistervalue-method.md)|`ICorDebugValue`하위 비트가 지정 된 레지스터에 저장 되 고 상위 비트가 지정 된 메모리 주소에 저장 되는 지역 변수의 값을 나타내는에 대 한 포인터를 가져옵니다.|  
|[GetLocalMemoryValue 메서드](icordebugnativeframe-getlocalmemoryvalue-method.md)|`ICorDebugValue`지정 된 메모리 주소에 저장 된 지역 변수의 값을 나타내는에 대 한 포인터를 가져옵니다.|  
|[GetLocalRegisterMemoryValue 메서드](icordebugnativeframe-getlocalregistermemoryvalue-method.md)|`ICorDebugValue`상위 비트가 지정 된 레지스터에 저장 되 고 하위 비트가 지정 된 메모리 주소에 저장 되는 지역 변수의 값을 나타내는에 대 한 포인터를 가져옵니다.|  
|[GetLocalRegisterValue 메서드](icordebugnativeframe-getlocalregistervalue-method.md)|`ICorDebugValue`지정 된 네이티브 레지스터에 저장 된 인수 또는 지역 변수의 값을 나타내는에 대 한 포인터를 가져옵니다.|  
|[GetRegisterSet 메서드](icordebugnativeframe-getregisterset-method.md)|이에 대 한 레지스터 집합을 나타내는 [ICorDebugRegisterSet](icordebugregisterset-interface.md) 에 대 한 포인터를 가져옵니다 `ICorDebugNativeFrame` .|  
|[SetIP 메서드](icordebugnativeframe-setip-method.md)|네이티브 코드에서 지정 된 오프셋 위치에 대 한 명령 포인터를 설정 합니다.|  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
> 이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [디버깅 인터페이스](debugging-interfaces.md)
