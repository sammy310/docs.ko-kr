---
title: IActionOnCLREvent::OnEvent 메서드
ms.date: 03/30/2017
api_name:
- IActionOnCLREvent.OnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IActionOnCLREvent::OnEvent
helpviewer_keywords:
- OnEvent method [.NET Framework hosting]
- IActionOnCLREvent::OnEvent method [.NET Framework hosting]
ms.assetid: 0970f10c-4304-4c12-91c0-83e51455afb4
topic_type:
- apiref
ms.openlocfilehash: bbf5e299285071ba6d43fd2c40fc724d19bc7b2a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504357"
---
# <a name="iactiononclreventonevent-method"></a>IActionOnCLREvent::OnEvent 메서드
[ICLROnEventManager:: RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) 메서드를 호출 하 여 등록 된 이벤트에 대해 콜백을 수행 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT OnEvent (  
    [in] EClrEvent event,  
    [in] PVOID     data  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `event`  
 진행 이벤트 유형을 나타내는 [EClrEvent](eclrevent-enumeration.md) 값 중 하나입니다.  
  
 `data`  
 진행 에 대 한 세부 정보를 포함 하는 개체에 대 한 포인터 `event` 입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`OnEvent`성공적으로 반환 되었습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다. 모든 호스팅 메서드에 대 한 후속 호출에서는 HOST_E_CLRNOTAVAILABLE을 반환 합니다.|  
  
## <a name="remarks"></a>설명  
 `data`매개 변수는 지정 되지 않은 형식의 개체에 대 한 포인터입니다. `event`매개 변수가 이면는 `Event_DomainUnload` `data` 언로드된의 숫자 식별자입니다 <xref:System.AppDomain> . 호스트는이 식별자를 키로 사용 하 여 적절 한 작업을 수행할 수 있습니다.  
  
 `event`가 인 `Event_MDAFired` 경우 `data` 는 MDA (관리 디버깅 도우미)의 메시지 출력을 포함 하는 [MDAInfo](mdainfo-structure.md) 인스턴스에 대 한 포인터입니다. Mda는 이벤트에 대 한 XML 메시지를 생성 하 여 개발자가 디버깅 하는 데 도움이 되는 CLR의 기능입니다. 이러한 메시지는 관리 코드와 비관리 코드 간의 전환을 디버깅 하는 데 특히 유용할 수 있습니다. 자세한 내용은 [관리 디버깅 도우미를 사용 하 여 오류 진단](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)을 참조 하세요.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [관리 디버깅 도우미를 사용하여 오류 진단](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [EClrEvent 열거형](eclrevent-enumeration.md)
- [IActionOnCLREvent 인터페이스](iactiononclrevent-interface.md)
- [ICLRControl 인터페이스](iclrcontrol-interface.md)
- [ICLROnEventManager 인터페이스](iclroneventmanager-interface.md)
- [MDAInfo 구조체](mdainfo-structure.md)
