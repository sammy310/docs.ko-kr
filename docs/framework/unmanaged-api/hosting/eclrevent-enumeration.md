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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 13d564be68d6b49a1616be97710312f33f828d48
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59176347"
---
# <a name="eclrevent-enumeration"></a>EClrEvent 열거형
호스트 콜백을 등록할 수 있는 공용 언어 런타임 (CLR) 이벤트를 설명 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
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
|`Event_ClrDisabled`|CLR 오류를 지정합니다.|  
|`Event_DomainUnload`|특정 언로드한다 지정 <xref:System.AppDomain>합니다.|  
|`Event_MDAFired`|관리 디버깅 도우미 (MDA) 메시지에 생성 되었음을 지정 합니다.|  
|`Event_StackOverflow`|스택 오버플로 오류가 발생을 지정 합니다.|  
  
## <a name="remarks"></a>설명  
 호스트에 설명 된 이벤트 형식에 대 한 콜백을 등록할 수 있습니다 `EClrEvent` 의 메서드를 호출 하 여 합니다 [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md) 인터페이스입니다. 호스트를 호출 하 여이 인터페이스에 대 한 포인터를 가져옵니다 합니다 [iclrcontrol:: Getclrmanager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) 메서드.  
  
 합니다 `Event_CLRDisabled` 및 `Event_DomainUnload` 이벤트가 두 번 이상 및는 언로드 또는 CLR의 비활성화를 알리기 위해 서로 다른 여러 스레드에서 발생할 수 있습니다.  
  
 합니다 `Event_MDAFired` 이벤트를 생성 시킵니다는 [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) MDA 메시지의 세부 정보를 포함 하는 인스턴스. Mda에 대 한 자세한 내용은 참조 하세요. [관리 디버깅 도우미를 사용 하 여 오류 진단](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [IActionOnCLREvent 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [ICLRControl 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [호스팅 열거형](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
