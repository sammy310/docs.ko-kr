---
description: '자세히 알아보기: ICorConfiguration 인터페이스'
title: ICorConfiguration 인터페이스
ms.date: 03/30/2017
api_name:
- ICorConfiguration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorConfiguration
helpviewer_keywords:
- ICorConfiguration interface [.NET Framework hosting]
ms.assetid: aaf96116-372b-4538-afb1-9e0fcdac1f98
topic_type:
- apiref
ms.openlocfilehash: f75e9e445c7fe4615abcae27756bcc420b5255b2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636691"
---
# <a name="icorconfiguration-interface"></a>ICorConfiguration 인터페이스

CLR (공용 언어 런타임)을 구성 하는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[AddDebuggerSpecialThread 메서드](icorconfiguration-adddebuggerspecialthread-method.md)|관리 되거나 관리 되지 않는 디버깅 시나리오에서 디버거가 응용 프로그램을 중지 하는 동안 특정 스레드가 계속 실행 되도록 허용 해야 하는 디버깅 서비스를 나타냅니다.|  
|[SetDebuggerThreadControl 메서드](icorconfiguration-setdebuggerthreadcontrol-method.md)|디버깅을 위해 CLR 스레드가 차단 되 고 차단 해제 될 때 디버깅 서비스에서 호출할 콜백 인터페이스를 설정 합니다.|  
|[SetGCHostControl 메서드](icorconfiguration-setgchostcontrol-method.md)|가비지 수집기에서 가상 메모리의 한도를 변경 하는 호스트를 요청 하는 데 사용할 콜백 인터페이스를 설정 합니다.|  
|[SetGCThreadControl 메서드](icorconfiguration-setgcthreadcontrol-method.md)|가비지 컬렉션에 대해 차단 되는 런타임 이외의 작업에 대해 스레드를 예약 하는 콜백 인터페이스를 설정 합니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [호스팅 인터페이스](hosting-interfaces.md)
- [CorRuntimeHost Coclass](corruntimehost-coclass.md)
