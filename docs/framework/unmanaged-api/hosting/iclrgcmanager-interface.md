---
title: ICLRGCManager 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRGCManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager
helpviewer_keywords:
- ICLRGCManager interface [.NET Framework hosting]
ms.assetid: fb511c9b-3fe4-41b0-822a-6ba4a079d1f5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b9519f7c2df5cf078bac6be038275527d7741edb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59152167"
---
# <a name="iclrgcmanager-interface"></a>ICLRGCManager 인터페이스
공용 언어 런타임의 가비지 컬렉션 시스템과 상호 작용 하는 데 사용 하는 메서드를 제공 합니다.  
  
> [!NOTE]
>  부터 합니다 [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]를 사용할 수는 [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) 가비지 수집 세그먼트의 크기 및 가비지 컬렉션 시스템의 0 세대의 최대 크기 값에 큰 설정 하는 방법 보다는 `DWORD` 에 의해 적용 되는 제한 된 [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) 메서드.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Collect 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-collect-method.md)|지정된 된 세대의 가비지 수집을 강제로 수행 합니다.|  
|[GetStats 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md)|가비지 컬렉션 시스템에 대 한 현재 통계의 집합을 가져옵니다.|  
|[SetGCStartupLimits 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md)|가비지 수집 세그먼트의 크기 및 가비지 컬렉션 시스템의 0 세대의 최대 크기를 설정합니다.|  
  
## <a name="remarks"></a>설명  
 관리 되는 가비지 수집 메커니즘을 구현 하는 CLR (공용 언어 런타임) <xref:System.GC> 형식입니다. 가비지 컬렉션 시스템에 대 한 자세한 내용은 참조 하세요. [가비지 수집](../../../../docs/standard/garbage-collection/index.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [자동 메모리 관리](../../../../docs/standard/automatic-memory-management.md)
- [COR_GC_STATS 구조체](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [ICLRControl 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [CLR 호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [호스팅](../../../../docs/framework/unmanaged-api/hosting/index.md)
