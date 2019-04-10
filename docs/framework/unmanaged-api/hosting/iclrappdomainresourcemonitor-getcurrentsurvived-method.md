---
title: ICLRAppDomainResourceMonitor::GetCurrentSurvived 메서드
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentSurvived
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentSurvived
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentSurvived method [.NET Framework hosting]
- GetCurrentSurvived method [.NET Framework hosting]
ms.assetid: 392e9009-40ef-40e3-ad4d-7ce93a989e78
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 408ef5419fbc2081d25ad442986ec8155bcb4c62
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59141546"
---
# <a name="iclrappdomainresourcemonitorgetcurrentsurvived-method"></a>ICLRAppDomainResourceMonitor::GetCurrentSurvived 메서드
마지막 전체 차단 가비지 수집에도 유지 되 고 현재 응용 프로그램 도메인에서 참조 되는 바이트 수를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT STDMETHODCALLTYPE GetCurrentSurvived(  
             [in]  DWORD dwAppDomainId,  
             [out] ULONGLONG *pAppDomainBytesSurvived,  
             [out] ULONGLONG *pTotalBytesSurvived);  
```  
  
## <a name="parameters"></a>매개 변수  
 `dwAppDomainId`  
 [in] 요청 된 응용 프로그램 도메인의 ID입니다.  
  
 `pAppDomainBytesSurvived`  
 [out] 이 응용 프로그램 도메인에서 보유 하는 마지막 가비지 컬렉션 후 남아 있는 바이트 수에 대 한 포인터입니다. 전체 수집 후이 번호는 정확 하 고 완료 합니다. 임시 수집 후이 수가 잠재적으로 완전 하지 않습니다. 이 매개 변수는 `null`일 수 있습니다.  
  
 `pRuntimeBytesSurvived`  
 [out] 마지막 가비지 수집에서 남아 있는 바이트의 총 수에 대 한 포인터입니다. 이 숫자를 전체 수집 후 관리 되는 힙이에 저장 된 바이트 수를 나타냅니다. 이 숫자를 임시 수집 후 임시 세대에서 실시간으로 저장 된 바이트 수를 나타냅니다. 이 매개 변수는 `null`일 수 있습니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|COR_E_APPDOMAINUNLOADED|응용 프로그램 도메인 언로드 되었습니다 또는 존재 하지 않습니다.|  
  
## <a name="remarks"></a>설명  
 전체 차단 가비지 컬렉션 후에 통계가 업데이트 즉, 수집 하는 동안 응용 프로그램을 중지 하는 모든 세대를 포함 하는 컬렉션에 발생 합니다. 예를 들어를 <xref:System.GC.Collect?displayProperty=nameWithType> 메서드 오버 로드는 전체 차단 컬렉션을 수행 합니다. 동시 가비지 컬렉션이 백그라운드에서 발생 하 고 응용 프로그램을 차단 하지 않습니다.  
  
 합니다 `GetCurrentSurvived` 메서드는 관리 되는 관리 되지 않는 해당 <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> 속성입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** MetaHost.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [ICLRAppDomainResourceMonitor 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [응용 프로그램 도메인 리소스 모니터링](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)
- [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [호스팅](../../../../docs/framework/unmanaged-api/hosting/index.md)
