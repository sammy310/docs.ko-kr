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
ms.openlocfilehash: ee749fd40f440e92f1d1b09c2ea5e7bdd51f1cbe
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131129"
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
|`Event_DomainUnload`|특정 <xref:System.AppDomain>의 언로드를 지정 합니다.|  
|`Event_MDAFired`|MDA (관리 디버깅 도우미) 메시지를 생성 하도록 지정 합니다.|  
|`Event_StackOverflow`|스택 오버플로 오류가 발생 했음을 지정 합니다.|  
  
## <a name="remarks"></a>주의  
 호스트는 [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md) 인터페이스의 메서드를 호출 하 여 `EClrEvent`에서 설명 하는 이벤트 형식에 대해 콜백을 등록할 수 있습니다. 호스트는 [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) 메서드를 호출 하 여이 인터페이스에 대 한 포인터를 가져옵니다.  
  
 `Event_CLRDisabled` 및 `Event_DomainUnload` 이벤트는 다른 스레드에서 두 번 이상 발생 하 여 언로드 또는 CLR 비활성화를 알릴 수 있습니다.  
  
 `Event_MDAFired` 이벤트는 MDA 메시지의 세부 정보가 포함 된 [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) 인스턴스 생성을 발생 시킵니다. Mda에 대 한 자세한 내용은 [관리 디버깅 도우미를 사용 하 여 오류 진단](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)을 참조 하세요.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [IActionOnCLREvent 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [ICLRControl 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [호스팅 열거형](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
