---
description: '자세히 알아보기: ICorDebugChain 인터페이스'
title: ICorDebugChain 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain
helpviewer_keywords:
- ICorDebugChain interface [.NET Framework debugging]
ms.assetid: f671f519-1cb3-4ae5-b9f1-abc5e783459f
topic_type:
- apiref
ms.openlocfilehash: 391c9a3e54d06d303728da5ab7f105bc8e2558ef
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661209"
---
# <a name="icordebugchain-interface"></a>ICorDebugChain 인터페이스

실제 또는 논리 호출 스택의 세그먼트를 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[EnumerateFrames 메서드](icordebugchain-enumerateframes-method.md)|최신 프레임에서 시작 하 여 체인의 모든 관리 되는 스택 프레임을 포함 하는 열거자를 가져옵니다.|  
|[GetActiveFrame 메서드](icordebugchain-getactiveframe-method.md)|체인의 활성 (가장 최근) 프레임을 가져옵니다.|  
|[GetCallee 메서드](icordebugchain-getcallee-method.md)|이 체인에 의해 호출 된 체인을 가져옵니다.|  
|[GetCaller 메서드](icordebugchain-getcaller-method.md)|이 체인을 호출한 체인을 가져옵니다.|  
|[GetContext 메서드](icordebugchain-getcontext-method.md)|구현되지 않았습니다.|  
|[GetNext 메서드](icordebugchain-getnext-method.md)|스레드에 대 한 다음 프레임 체인을 가져옵니다.|  
|[GetPrevious 메서드](icordebugchain-getprevious-method.md)|스레드에 대 한 이전 프레임 체인을 가져옵니다.|  
|[GetReason 메서드](icordebugchain-getreason-method.md)|이 호출 체인의 genesis 이유를 가져옵니다.|  
|[GetRegisterSet 메서드](icordebugchain-getregisterset-method.md)|이 체인의 활성 부분에 대 한 레지스터 집합을 가져옵니다.|  
|[GetStackRange 메서드](icordebugchain-getstackrange-method.md)|이 체인의 스택 세그먼트에 대 한 주소 범위를 가져옵니다.|  
|[GetThread 메서드](icordebugchain-getthread-method.md)|이 호출 체인이 속한 실제 스레드를 가져옵니다.|  
|[IsManaged 메서드](icordebugchain-ismanaged-method.md)|이 체인이 관리 코드를 실행 하 고 있는지 여부를 나타내는 값을 가져옵니다.|  
  
## <a name="remarks"></a>설명  

 체인의 스택 프레임은 연속 된 스택 공간을 차지 하 고 동일한 스레드와 컨텍스트를 공유 합니다. 체인은 관리 코드 체인 또는 비관리 코드 체인을 나타낼 수 있습니다. 빈 `ICorDebugChain` 인스턴스는 관리 되지 않는 코드 체인을 나타냅니다.  
  
> [!NOTE]
> 이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [디버깅 인터페이스](debugging-interfaces.md)
