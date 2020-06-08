---
title: EClrEvent 열거형
ms.date: 03/30/2017
api_name:
- EClrEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrEvent
helpviewer_keywords:
- EClrEvent enumeration [.NET Framework hosting]
ms.assetid: 7c36a7c2-75a2-4971-bc23-abf54c812154
topic_type:
- apiref
ms.openlocfilehash: 3ecaebb9d943a3cdbb231307012b5dc3aaf000f7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493419"
---
# <a name="eclrevent-enumeration"></a>EClrEvent 열거형
호스트가 콜백을 등록할 수 있는 CLR (공용 언어 런타임) 이벤트에 대해 설명 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum {  
    Event_ClrDisabled,  
    Event_DomainUnload,  
    Event_MDAFired,  
    Event_StackOverflow  
} EClrEvent;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`Event_ClrDisabled`|심각한 CLR 오류를 지정 합니다.|  
|`Event_DomainUnload`|특정의 언로드를 지정 합니다 <xref:System.AppDomain> .|  
|`Event_MDAFired`|MDA (관리 디버깅 도우미) 메시지를 생성 하도록 지정 합니다.|  
|`Event_StackOverflow`|스택 오버플로 오류가 발생 했음을 지정 합니다.|  
  
## <a name="remarks"></a>설명  
 호스트는 `EClrEvent` [ICLROnEventManager](iclroneventmanager-interface.md) 인터페이스의 메서드를 호출 하 여에서 설명 하는 이벤트 형식에 대해 콜백을 등록할 수 있습니다. 호스트는 [ICLRControl:: GetCLRManager](iclrcontrol-getclrmanager-method.md) 메서드를 호출 하 여이 인터페이스에 대 한 포인터를 가져옵니다.  
  
 `Event_CLRDisabled`및 `Event_DomainUnload` 이벤트는 서로 다른 스레드에서 두 번 이상 발생 하거나 CLR을 사용 하지 않도록 설정 하거나 언로드할 때 신호를 보낼 수 있습니다.  
  
 `Event_MDAFired`이벤트는 MDA 메시지의 세부 정보가 포함 된 [MDAInfo](mdainfo-structure.md) 인스턴스 만들기를 발생 시킵니다. Mda에 대 한 자세한 내용은 [관리 디버깅 도우미를 사용 하 여 오류 진단](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)을 참조 하세요.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IActionOnCLREvent 인터페이스](iactiononclrevent-interface.md)
- [ICLRControl 인터페이스](iclrcontrol-interface.md)
- [호스팅 열거형](hosting-enumerations.md)
