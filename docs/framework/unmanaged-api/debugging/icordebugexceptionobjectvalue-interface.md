---
description: '자세히 알아보기: ICorDebugExceptionObjectValue 인터페이스'
title: ICorDebugExceptionObjectValue 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectValue
helpviewer_keywords:
- ICorDebugExceptionObjectValue interface [.NET Framework debugging]
ms.assetid: 43416dd5-8892-4106-9f59-f9143b19ddb4
topic_type:
- apiref
ms.openlocfilehash: 67672f9921bab31019a42b742480176e6d0bf3d4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693202"
---
# <a name="icordebugexceptionobjectvalue-interface"></a>ICorDebugExceptionObjectValue 인터페이스

"ICorDebugObjectValue" 인터페이스를 확장 하 여 관리 되는 예외 개체의 스택 추적 정보를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[EnumerateExceptionCallStack 메서드](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)|예외 개체에 포함 된 호출 스택에 대 한 열거자를 가져옵니다.|  
  
## <a name="remarks"></a>설명  

 `QueryInterface`에서 파생 된 관리 되는 개체에 대 한 호출이 성공 합니다 <xref:System.Exception?displayProperty=nameWithType> .  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [디버깅 인터페이스](debugging-interfaces.md)
- [디버깅](index.md)
