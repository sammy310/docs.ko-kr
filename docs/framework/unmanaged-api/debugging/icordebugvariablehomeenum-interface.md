---
description: '자세히 알아보기: ICorDebugVariableHomeEnum 인터페이스'
title: ICorDebugVariableHomeEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHomeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHomeEnum
helpviewer_keywords:
- ICorDebugVariableHomeEnum interface [.NET Framework debugging]
ms.assetid: c312ae6d-c8dc-48d6-9f1e-ead515c88fdf
topic_type:
- apiref
ms.openlocfilehash: c56c68a6b5f9d329fe8af23f47b40fa629bfe3ba
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790622"
---
# <a name="icordebugvariablehomeenum-interface"></a>ICorDebugVariableHomeEnum 인터페이스

함수의 지역 변수 및 인수에 대 한 열거자를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Next 메서드](icordebugvariablehomeenum-next-method.md)|함수의 지역 변수 및 인수에 대 한 정보를 포함 하는 지정 된 수의 [ICorDebugVariableHome](icordebugvariablehome-interface.md) 인스턴스를 가져옵니다.|  
  
## <a name="remarks"></a>설명  

 `ICorDebugVariableHomeEnum`인터페이스는 ICorDebugEnum 인터페이스를 구현 합니다.  
  
 `ICorDebugVariableHomeEnum`인스턴스는 [ICorDebugCode4:: EnumerateVariableHomes](icordebugcode4-enumeratevariablehomes-method.md) 메서드를 호출 하 여 [ICorDebugVariableHome](icordebugvariablehome-interface.md) 인스턴스로 채워집니다. 컬렉션의 각 [ICorDebugVariableHome](icordebugvariablehome-interface.md) 인스턴스는 함수의 지역 변수 또는 인수를 나타냅니다. 컬렉션의  [ICorDebugVariableHome](icordebugvariablehome-interface.md) 개체는 [ICorDebugVariableHomeEnum:: Next](icordebugvariablehomeenum-next-method.md) 메서드를 호출 하 여 열거할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorDebugVariableHome 인터페이스](icordebugvariablehome-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
