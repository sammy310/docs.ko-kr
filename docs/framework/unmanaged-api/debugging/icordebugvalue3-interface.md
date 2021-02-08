---
description: '자세히 알아보기: ICorDebugValue3 인터페이스'
title: ICorDebugValue3 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugValue3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue3
helpviewer_keywords:
- ICorDebugValue3 interface [.NET Framework debugging]
ms.assetid: 7d5385d3-f4a5-47c4-8478-a3513b5e9406
topic_type:
- apiref
ms.openlocfilehash: e5868b91d23426a2d8dd8fed87b13ec61fef95ef
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794652"
---
# <a name="icordebugvalue3-interface"></a>ICorDebugValue3 인터페이스

"ICorDebugValue" 및 "ICorDebugValue2" 인터페이스를 확장 하 여 2gb 보다 큰 배열에 대 한 지원을 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetSize64 메서드](icordebugvalue3-getsize64-method.md)|이 개체의 크기 (바이트)를 가져옵니다 `ICorDebugValue3` .|  
  
## <a name="remarks"></a>설명  

 [ICorDebugValue:: GetSize](icordebugvalue3-getsize64-method.md) 메서드는 0 바이트에서 2147483647 바이트 범위의 개체 크기를 반환 합니다. .NET Framework 4.5에서 배열의 크기는 2gb를 초과할 수 있습니다. `ICorDebugValue3`인터페이스를 사용 하면 이러한 배열의 크기를 확인할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [디버깅 인터페이스](debugging-interfaces.md)
- [디버깅](index.md)
