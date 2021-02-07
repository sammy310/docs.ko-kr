---
description: '자세히 알아보기: ICorDebugFunction2 인터페이스'
title: ICorDebugFunction2 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2
helpviewer_keywords:
- ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 2b936bef-9b75-48bf-859f-42e419c65f1c
topic_type:
- apiref
ms.openlocfilehash: e5297d46acb9b174537363fc185fa2d540d55a75
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692201"
---
# <a name="icordebugfunction2-interface"></a>ICorDebugFunction2 인터페이스

ICorDebugFunction 인터페이스를 논리적으로 확장 하 여 사용자가 지정 하지 않은 코드를 건너뛰는 내 코드만 단계별 디버깅을 지원 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[EnumerateNativeCode 메서드](icordebugfunction2-enumeratenativecode-method.md)|아직 구현 되지 않았습니다. 이 ICorDebugFunction2 개체가 참조 하는 함수에 네이티브 코드 문이 포함 된 ICorDebugCodeEnum에 대 한 인터페이스 포인터를 가져옵니다.|  
|[GetJMCStatus 메서드](icordebugfunction2-getjmcstatus-method.md)|이 함수가 사용자 코드로 표시 되었는지 여부를 나타내는 값을 가져옵니다.|  
|[GetVersionNumber 메서드](icordebugfunction2-getversionnumber-method.md)|이 함수의 편집 하며 계속 하기 버전을 가져옵니다.|  
|[SetJMCStatus 메서드](icordebugfunction2-setjmcstatus-method.md)|내 코드만 단계별 실행을 위해이 함수를 표시 합니다.|  
  
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
