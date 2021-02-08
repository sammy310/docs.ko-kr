---
description: '자세한 정보: IHostTask 인터페이스'
title: IHostTask 인터페이스
ms.date: 03/30/2017
api_name:
- IHostTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask
helpviewer_keywords:
- IHostTask interface [.NET Framework hosting]
ms.assetid: a71dbbd5-64b8-47eb-9f03-8e8c85fbe2bc
topic_type:
- apiref
ms.openlocfilehash: c46bbdd2e881c20d1ffd634bec8ddfa3b70b0f82
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784667"
---
# <a name="ihosttask-interface"></a>IHostTask 인터페이스

CLR (공용 언어 런타임)이 호스트와 통신 하 여 작업을 관리 하는 데 사용할 수 있는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Alert 메서드](ihosttask-alert-method.md)|호스트가 현재 인스턴스로 표시 된 작업의 절전 모드를 해제 `IHostTask` 하도록 요청 하므로 작업이 중단 될 수 있습니다.|  
|[GetPriority 메서드](ihosttask-getpriority-method.md)|현재 인스턴스가 나타내는 작업의 스레드 우선 순위 수준을 가져옵니다 `IHostTask` .|  
|[Join 메서드](ihosttask-join-method.md)|현재 인스턴스가 나타내는 작업이 `IHostTask` 완료 되거나 지정 된 시간 간격이 경과 되거나 [IHostTask:: Alert](ihosttask-alert-method.md) 이 호출 될 때까지 호출 작업을 차단 합니다.|  
|[SetCLRTask 메서드](ihosttask-setclrtask-method.md)|[ICLRTask 인터페이스](iclrtask-interface.md) 인스턴스를 현재 `IHostTask` 인스턴스와 연결 합니다.|  
|[SetPriority 메서드](ihosttask-setpriority-method.md)|호스트가 현재 인스턴스로 표시 되는 작업에 대 한 스레드 우선 순위 수준을 조정 하도록 요청 합니다 `IHostTask` .|  
|[Start 메서드](ihosttask-start-method.md)|현재 인스턴스가 나타내는 작업을 `IHostTask` 일시 중단 상태에서 활성 상태로 전환 하 여 코드를 실행할 수 있도록 요청 합니다.|  
  
## <a name="remarks"></a>설명  

 CLR은에 의해 정의 된 메서드를 호출 `IHostTask` 하 여 작업을 시작 하 고, 스레드 우선 순위 수준을 설정 하는 등의 작업을 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRTask 인터페이스](iclrtask-interface.md)
- [ICLRTaskManager 인터페이스](iclrtaskmanager-interface.md)
- [IHostTaskManager 인터페이스](ihosttaskmanager-interface.md)
- [호스팅 인터페이스](hosting-interfaces.md)
