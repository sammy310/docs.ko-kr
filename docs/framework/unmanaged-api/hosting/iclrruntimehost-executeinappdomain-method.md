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
ms.openlocfilehash: 4c28c4a5cc64b20c9ac9c57e1aef5e7b90a20e01
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728890"
---
# <a name="iclrruntimehostexecuteinappdomain-method"></a>ICLRRuntimeHost::ExecuteInAppDomain 메서드

지정 된 <xref:System.AppDomain> 관리 코드를 실행할를 지정 합니다.  
  
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
 진행 지정 된 메서드를 실행할의 숫자 ID입니다 <xref:System.AppDomain> .  
  
 `pCallback`  
 진행 지정 된 내에서 실행할 함수에 대 한 포인터입니다 <xref:System.AppDomain> .  
  
 `cookie`  
 진행 호출자가 할당 한 불투명 메모리에 대 한 포인터입니다. 이 매개 변수는 CLR (공용 언어 런타임)에서 도메인 콜백에 전달 됩니다. 런타임 관리 힙 메모리가 아닙니다. 이 메모리의 할당 및 수명은 모두 호출자에 의해 제어 됩니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`ExecuteInAppDomain` 성공적으로 반환 되었습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
  
## <a name="remarks"></a>설명  

 `ExecuteInAppDomain` 호스트에서 <xref:System.AppDomain> 지정 된 관리 되는 메서드를 실행 해야 하는 관리를 제어할 수 있습니다. <xref:System.AppDomain.Id%2A> [GetCurrentAppDomainId 메서드](iclrruntimehost-getcurrentappdomainid-method.md)를 호출 하 여 속성의 값에 해당 하는 응용 프로그램 도메인 식별자의 값을 가져올 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRRuntimeHost 인터페이스](iclrruntimehost-interface.md)
