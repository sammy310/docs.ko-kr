---
description: '자세히 알아보기: ICLRAppDomainResourceMonitor:: GetCurrentCpuTime 메서드'
title: ICLRAppDomainResourceMonitor::GetCurrentCpuTime 메서드
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentCpuTime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentCpuTime
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentCpuTime method [.NET Framework hosting]
- GetCurrentCpuTime method [.NET Framework hosting]
ms.assetid: ebc9cc33-fcd6-4cae-9ecb-ea21c51874e6
topic_type:
- apiref
ms.openlocfilehash: ce36bf4ab88f953834d3ff12404bcaadcb42812d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753931"
---
# <a name="iclrappdomainresourcemonitorgetcurrentcputime-method"></a>ICLRAppDomainResourceMonitor::GetCurrentCpuTime 메서드

응용 프로그램 도메인이 만들어진 후 현재 응용 프로그램 도메인에서 실행 되는 동안 모든 스레드에서 사용 된 총 프로세서 시간을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetCurrentCpuTime([in]  DWORD dwAppDomainId,  
                          [out] ULONGLONG* pMilliseconds);  
```  
  
## <a name="parameters"></a>매개 변수  

 `dwAppDomainId`  
 진행 요청 된 응용 프로그램 도메인의 ID입니다.  
  
 `pMilliseconds`  
 제한이 응용 프로그램 도메인이 만들어진 후 현재 응용 프로그램 도메인에서 실행 되는 동안 모든 스레드에서 사용 된 총 프로세서 시간에 대 한 포인터입니다. 이 매개 변수는 `null`일 수 있습니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|COR_E_APPDOMAINUNLOADED|응용 프로그램 도메인이 언로드 되었거나 존재 하지 않습니다.|  
|E_FAIL|응용 프로그램 도메인 리소스 모니터링이 사용 하도록 설정 되어 있지 않습니다.<br /><br /> 또는<br /><br /> 다른 모든 오류입니다.|  
  
## <a name="remarks"></a>설명  

 이 메서드는 관리 되는 속성에 해당 하는 관리 되지 않는 <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> 속성입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MetaHost  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRAppDomainResourceMonitor 인터페이스](iclrappdomainresourcemonitor-interface.md)
- [호스팅 인터페이스](hosting-interfaces.md)
- [응용 프로그램 도메인 리소스 모니터링](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [호스팅](index.md)
