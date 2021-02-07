---
description: '자세히 알아보기: ICorDebugRegisterSet 인터페이스'
title: ICorDebugRegisterSet 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet
helpviewer_keywords:
- ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: d3d9676d-0b87-4bc3-b679-7bbc7a186c88
topic_type:
- apiref
ms.openlocfilehash: 7d888e9e395e9f5fa88c6a6d96b2b8e3171ef4ac
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690784"
---
# <a name="icordebugregisterset-interface"></a>ICorDebugRegisterSet 인터페이스

현재 코드를 실행 중인 컴퓨터에서 사용할 수 있는 레지스터 집합을 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetRegisters 메서드](icordebugregisterset-getregisters-method.md)|비트 마스크로 지정 된 각 레지스터의 값 (현재 코드를 실행 중인 컴퓨터)을 가져옵니다.|  
|[GetRegistersAvailable 메서드](icordebugregisterset-getregistersavailable-method.md)|현재 사용할 수 있는 레지스터를 나타내는 비트 마스크를 가져옵니다 `ICorDebugRegisterSet` .|  
|[GetThreadContext 메서드](icordebugregisterset-getthreadcontext-method.md)|현재 스레드의 컨텍스트를 가져옵니다.|  
|[SetRegisters 메서드](icordebugregisterset-setregisters-method.md)|.NET Framework 버전 2.0에 대해 구현 되지 않았습니다.|  
|[SetThreadContext 메서드](icordebugregisterset-setthreadcontext-method.md)|.NET Framework 2.0에 대해 구현 되지 않았습니다.|  
  
## <a name="remarks"></a>설명  

 `ICorDebugRegisterSet`인터페이스는 32 비트 레지스터만 지원 합니다. 추가 레지스터가 필요한 IA-64와 같은 플랫폼에서 [ICorDebugRegisterSet2](icordebugregisterset2-interface.md) 인터페이스를 사용 합니다.  
  
> [!NOTE]
> 이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [디버깅 인터페이스](debugging-interfaces.md)
- [ICorDebugRegisterSet2 인터페이스](icordebugregisterset2-interface.md)
