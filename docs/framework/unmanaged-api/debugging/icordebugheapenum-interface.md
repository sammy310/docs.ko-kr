---
description: '자세히 알아보기: ICorDebugHeapEnum 인터페이스'
title: ICorDebugHeapEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugHeapEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapEnum
helpviewer_keywords:
- ICorDebugHeapEnum interface [.NET Framework debugging]
ms.assetid: 99cbc1eb-d539-4f76-a0d8-b93348112f14
topic_type:
- apiref
ms.openlocfilehash: c8a2f46bf412e2c4b2fe43d3eb50169191f40445
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660897"
---
# <a name="icordebugheapenum-interface"></a>ICorDebugHeapEnum 인터페이스

관리되는 힙의 개체에 대한 열거자를 제공합니다. 이 인터페이스는 ICorDebugEnum 인터페이스의 서브클래스입니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Next 메서드](icordebugheapenum-next-method.md)|관리 되는 힙의 개체에 대 한 정보를 포함 하는 지정 된 수의 [COR_HEAPOBJECT](cor-heapobject-structure.md) 인스턴스를 가져옵니다.|  
  
## <a name="remarks"></a>설명  

 `ICorDebugHeapEnum`인터페이스는 ICorDebugEnum 인터페이스를 구현 합니다.  
  
 `ICorDebugHeapEnum` [ICorDebugProcess5:: EnumerateHeap](icordebugprocess5-enumerateheap-method.md) 메서드를 호출 하 여 인스턴스가 [COR_HEAPOBJECT](cor-heapobject-structure.md) 인스턴스로 채워집니다. 컬렉션의 각 [COR_HEAPOBJECT](cor-heapobject-structure.md) 인스턴스는 힙의 라이브 개체 또는 개체가 루 팅 되지 않았지만 가비지 수집기에서 아직 수집 되지 않은 개체를 나타냅니다. [ICorDebugHeapEnum:: Next](icordebugheapenum-next-method.md) 메서드를 호출 하 여 컬렉션의 [COR_HEAPOBJECT](cor-heapobject-structure.md) 개체를 열거할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [디버깅 인터페이스](debugging-interfaces.md)
