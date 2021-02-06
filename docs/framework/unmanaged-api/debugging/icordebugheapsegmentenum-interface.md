---
description: '자세히 알아보기: ICorDebugHeapSegmentEnum 인터페이스'
title: ICorDebugHeapSegmentEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugHealRegionEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapSegmentEnum
helpviewer_keywords:
- ICorDebugHeapSegmentEnum interface [.NET Framework debugging]
ms.assetid: 20fc1b9d-e228-4107-bd76-53934c1724b9
topic_type:
- apiref
ms.openlocfilehash: 614bae0ea5e3eb7816fdeec23a0dc7aa6e44801d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660884"
---
# <a name="icordebugheapsegmentenum-interface"></a>ICorDebugHeapSegmentEnum 인터페이스

관리되는 힙 메모리 영역에 대한 열거자를 제공합니다. 이 인터페이스는 ICorDebugEnum 인터페이스의 서브클래스입니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Next 메서드](icordebugheapsegmentenum-next-method.md)|관리 되는 힙의 영역에 대 한 정보를 포함 하는 지정 된 수의 [COR_SEGMENT](cor-segment-structure.md) 인스턴스를 가져옵니다.|  
  
## <a name="remarks"></a>설명  

 `ICorDebugHeapSegmentEnum`인터페이스는 ICorDebugEnum 인터페이스를 구현 합니다.  
  
 `ICorDebugHeapSegmentEnum` [ICorDebugProcess5:: EnumerateHeapRegions](icordebugprocess5-enumerateheapregions-method.md) 메서드를 호출 하 여 인스턴스가 [COR_SEGMENT](cor-segment-structure.md) 인스턴스로 채워집니다. [ICorDebugHeapSegmentEnum:: Next](icordebugheapsegmentenum-next-method.md) 메서드를 호출 하 여 컬렉션의 [COR_SEGMENT](cor-segment-structure.md) 개체를 열거할 수 있습니다.  
  
 `ICorDebugHeapSegmentEnum`컬렉션 개체는 관리 되는 개체를 포함할 수 있는 모든 메모리 영역을 열거 하지만 관리 되는 개체를 실제로 해당 지역에 배치 하는 것을 보장 하지는 않습니다. 여기에는 비어 있거나 예약 된 메모리 영역에 대 한 정보가 포함 될 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [디버깅 인터페이스](debugging-interfaces.md)
