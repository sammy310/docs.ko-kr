---
title: EPolicyAction 열거형
ms.date: 03/30/2017
api_name:
- EPolicyAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EPolicyAction
helpviewer_keywords:
- EPolicyAction enumeration [.NET Framework hosting]
ms.assetid: 72dd76ba-239e-45ac-9ded-318fb07d6c6d
topic_type:
- apiref
ms.openlocfilehash: 72b371d72b2f055f2840da5595d9022ffd7e2507
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674751"
---
# <a name="epolicyaction-enumeration"></a>EPolicyAction 열거형

[EClrOperation](eclroperation-enumeration.md) 및 [EClrFailure](eclrfailure-enumeration.md)에서 설명 하는 오류에 설명 된 작업에 대해 호스트가 설정할 수 있는 정책 작업에 대해 설명 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum {  
    eNoAction,  
    eThrowException,  
    eAbortThread,  
    eRudeAbortThread,  
    eUnloadAppDomain,  
    eRudeUnloadAppDomain,  
    eExitProcess,  
    eFastExitProcess,  
    eRudeExitProcess,  
    eDisableRuntime  
} EPolicyAction;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`eAbortThread`|CLR (공용 언어 런타임)이 스레드를 정상적으로 중단 하도록 지정 합니다. 정상적인 abort는 모든 `finally` 블록, `catch` 스레드 중단과 관련 된 모든 블록 및 종료자를 실행 하려는 시도를 포함 합니다.|  
|`eDisableRuntime`|CLR이 비활성화 상태를 시작 하도록 지정 합니다. 영향을 받는 프로세스에서 더 이상 관리 코드를 실행할 수 없으며, 스레드가 CLR에 시작 되지 않도록 차단 됩니다.|  
|`eExitProcess`|CLR에서 종료자 실행, 정리 및 로깅 작업 수행을 포함 하 여 프로세스의 정상적인 종료를 시도 하도록 지정 합니다.|  
|`eFastExitProcess`|종료자를 실행 하거나 정리 및 로깅 작업을 수행 하지 않고 CLR에서 즉시 프로세스를 종료 하도록 지정 합니다. 그러나 알림이 디버거로 전송 됩니다.|  
|`eNoAction`|아무 동작도 수행 하지 않도록 지정 합니다.|  
|`eRudeAbortThread`|CLR에서 잘못 된 스레드 중단을 수행 하도록 지정 합니다. `catch` `finally` 로 표시 된 및 블록만 <xref:System.EnterpriseServices.MustRunInClientContextAttribute> 실행 됩니다.|  
|`eRudeExitProcess`|CLR에서 종료자 또는 로깅 작업을 실행 하지 않고 프로세스를 종료 하도록 지정 합니다.|  
|`eRudeUnloadAppDomain`|CLR에서의 잘못 된 언로드를 수행 하도록 지정 합니다 <xref:System.AppDomain> . 로 표시 된 종료자만 <xref:System.EnterpriseServices.MustRunInClientContextAttribute> 실행 됩니다. 마찬가지로, 해당 스택에서이를 포함 하는 모든 스레드 <xref:System.AppDomain> 는를 수신 `ThreadAbortException` 하지만 `catch` `finally` 로 표시 된 및 블록만 <xref:System.EnterpriseServices.MustRunInClientContextAttribute> 실행 됩니다.|  
|`eThrowException`|조건에 적합 한 예외 (예: 메모리 부족, 버퍼 오버플로 등)를 throw 하도록 지정 합니다.|  
|`eUnloadAppDomain`|을 언로드하기 위해 지정 합니다 <xref:System.AppDomain> . CLR에서 종료자를 실행 하려고 합니다.|  
  
## <a name="remarks"></a>설명  

 호스트는 [ICLRPolicyManager](iclrpolicymanager-interface.md) 인터페이스의 메서드를 호출 하 여 정책 작업을 설정 합니다. 강제 및 정상적인 중단에 대 한 자세한 내용은 [EClrOperation](eclroperation-enumeration.md) 열거형을 참조 하세요.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [EClrFailure 열거형](eclrfailure-enumeration.md)
- [ICLRPolicyManager 인터페이스](iclrpolicymanager-interface.md)
- [IHostPolicyManager 인터페이스](ihostpolicymanager-interface.md)
- [호스팅 열거형](hosting-enumerations.md)
