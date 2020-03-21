---
title: ICLRRuntimeHost::ExecuteInAppDomain 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteInAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteInAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInAppDomain method [.NET Framework hosting]
- ExecuteInAppDomain method [.NET Framework hosting]
ms.assetid: e2b0e2db-3fae-4b56-844e-d30a125a660c
topic_type:
- apiref
ms.openlocfilehash: c012e4e2b5e41737f7bbe6a0fb887693b0ba22c8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176424"
---
# <a name="iclrruntimehostexecuteinappdomain-method"></a>ICLRRuntimeHost::ExecuteInAppDomain 메서드
<xref:System.AppDomain> 지정된 관리 코드를 실행할 수 있는 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ExecuteInAppDomain(  
    [in] DWORD AppDomainId,
    [in] FExecuteInDomainCallback pCallback,
    [in] void* cookie  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `AppDomainId`  
 【인】 지정된 메서드를 <xref:System.AppDomain> 실행할 수 있는 숫자 ID입니다.  
  
 `pCallback`  
 【인】 지정된 <xref:System.AppDomain>내에서 실행할 함수에 대한 포인터입니다.  
  
 `cookie`  
 【인】 불투명 호출자 할당 메모리에 대한 포인터입니다. 이 매개 변수는 공통 언어 런타임(CLR)을 통해 도메인 콜백으로 전달됩니다. 런타임 관리 힙 메모리가 아닙니다. 이 메모리의 할당과 수명은 모두 호출자에 의해 제어됩니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|`ExecuteInAppDomain`성공적으로 반환됩니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR이 프로세스에 로드되지 않았거나 CLR이 관리 코드를 실행하거나 호출을 성공적으로 처리할 수 없는 상태입니다.|  
|HOST_E_TIMEOUT|통화 시간이 시간 미정으로 확인되었습니다.|  
|HOST_E_NOT_OWNER|호출자는 잠금을 소유하지 않습니다.|  
|HOST_E_ABANDONED|차단된 스레드 또는 파이버가 대기하는 동안 이벤트가 취소되었습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생했습니다. 메서드가 E_FAIL 반환하면 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다. 호스팅 메서드에 대한 후속 호출은 HOST_E_CLRNOTAVAILABLE 반환합니다.|  
  
## <a name="remarks"></a>설명  
 `ExecuteInAppDomain`을 사용하면 호스트가 지정된 <xref:System.AppDomain> 관리 방법을 실행해야 하는 관리되는 제어 권한을 행사할 수 있습니다. <xref:System.AppDomain.Id%2A> [GetCurrentAppDomainId 메서드를](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)호출하여 속성 값에 해당하는 응용 프로그램 도메인의 식별자 값을 얻을 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MSCorE.h  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRRuntimeHost 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
