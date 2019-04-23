---
title: ICLRDebugManager 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRDebugManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager
helpviewer_keywords:
- ICLRDebugManager interface [.NET Framework hosting]
ms.assetid: e835062c-c7d6-4945-8a44-2de7ebf3928e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 22c3a480e2b68377e300df1083b3178ee4e2d2a9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59198844"
---
# <a name="iclrdebugmanager-interface"></a>ICLRDebugManager 인터페이스
호스트 식별자 및 이름을 사용 하 여 작업 집합을 연결 하는 데 사용할 수 있는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[BeginConnection 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)|작업 식별자 및 이름을 사용 하 여 연결 하려면 호스트와 디버거 간의 새 연결을 설정 합니다.|  
|[EndConnection 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)|작업 목록 및 식별자 및 이름을 간의 연결을 제거합니다.|  
|[GetDacl 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-getdacl-method.md)|이 메서드가 구현되지 않았습니다.|  
|[IsDebuggerAttached 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-isdebuggerattached-method.md)|디버거가 프로세스에 연결되어 있는지 여부를 나타내는 값을 가져옵니다.|  
|[SetConnectionTasks 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)|연결 목록을 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 식별자 및 이름을 사용 하 여 인스턴스.|  
|[SetDacl 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setdacl-method.md)|이 메서드가 구현되지 않았습니다.|  
|[SetSymbolReadingPolicy 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md)|프로그램 데이터베이스 (PDB) 파일을 읽기 위한 정책을 설정 합니다. 정책은 호출 스택의 줄 번호 및 파일에 대 한 정보 포함 되는지 여부를 결정 합니다.|  
  
## <a name="remarks"></a>설명  
 디버깅 시나리오에서 호스트 자체 프로그래밍 논리에 따라 작업을 그룹화 하려고 합니다. 예를 들어, 그룹화를 개발자가 프로세스에서 실행 중인 작업을 확인 하는 대신 개발자가 Api에 필요한 작업만 표시를 사용 합니다. `ICLRDebugManager` 이 유형의 그룹화를 구현 하는 호스트 수 있습니다.  
  
> [!IMPORTANT]
>  세 `ICLRDebugManager` 메서드를 `BeginConnection`를 `SetConnectionTasks` 및 `EndConnection`, 서로 종속 됩니다. 예상 대로 작동 하는 지정 된 순서로 호출 해야만 합니다.  
  
 그룹화 식별자 및 호스트를 그룹에 할당 하는 이름을 CLR (공용 언어 런타임)에 대 한 다음과 의미가 없습니다. CLR은 디버거를 따라 정보를 전달 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
