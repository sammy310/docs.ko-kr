---
title: IGCHost 인터페이스
ms.date: 03/30/2017
api_name:
- IGCHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost
helpviewer_keywords:
- IGCHost interface [.NET Framework hosting]
ms.assetid: 9ad70ffd-6963-4ab2-8c84-3d86c3fb8deb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3202aa25261863dae953e3edac36f3406fa001d8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59228175"
---
# <a name="igchost-interface"></a>IGCHost 인터페이스
가비지 컬렉션 시스템에 대 한 정보를 얻기 위한 고 가비지 컬렉션의 일부 측면을 제어 하기 위한 메서드를 제공 합니다.  
  
> [!NOTE]
>  부터 [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]를 사용할 수는 [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) 가비지 수집 세그먼트의 크기 및 가비지 컬렉션 시스템의 0 세대의 최대 크기 값 보다 큰으로 설정 하는 방법의 `DWORD` 에 의해 적용 되는 제한 된 [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md) 메서드.  
  
> [!NOTE]
>  이 인터페이스는 전문가 전용입니다. 부적절 하 게 사용 하는 경우에 응용 프로그램의 성능 영향을 수 있습니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Collect 메서드](../../../../docs/framework/unmanaged-api/hosting/igchost-collect-method.md)|현재 가비지 컬렉션의 상태에 관계 없이 지정된 된 세대에 발생 하는 수집을 강제로 실행 합니다.|  
|[GetStats 메서드](../../../../docs/framework/unmanaged-api/hosting/igchost-getstats-method.md)|가비지 컬렉션 시스템의 현재 상태에 대 한 통계를 가져옵니다.|  
|[GetThreadStats 메서드](../../../../docs/framework/unmanaged-api/hosting/igchost-getthreadstats-method.md)|가비지 컬렉션에 대 한 스레드당 통계를 가져옵니다.|  
|[SetGCStartupLimits 메서드](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md)|0 세대에 대 한 세그먼트 크기 및 최대 크기를 설정합니다.|  
|[SetVirtualMemLimit 메서드](../../../../docs/framework/unmanaged-api/hosting/igchost-setvirtualmemlimit-method.md)|런타임의 가상 메모리의 최대 크기를 설정합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** GCHost.idl, GCHost.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [CorRuntimeHost Coclass](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
