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
ms.openlocfilehash: dbe3df6bb20e5ad8f9eb534a366405eb9c33984f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678248"
---
# <a name="iclrgcmanager-interface"></a>ICLRGCManager 인터페이스

호스트가 공용 언어 런타임의 가비지 수집 시스템과 상호 작용할 수 있도록 하는 메서드를 제공 합니다.  
  
> [!NOTE]
> 4.5 .NET Framework부터 [ICLRGCManager2:: SetGCStartupLimitsEx](iclrgcmanager2-setgcstartuplimitsex-method.md) 메서드를 사용 하 여 가비지 수집 세그먼트의 크기와 가비지 수집 시스템의 최대 크기를 `DWORD` [SetGCStartupLimits](iclrgcmanager-setgcstartuplimits-method.md) 메서드에서 적용 되는 제한 보다 큰 값으로 설정할 수 있습니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Collect 메서드](iclrgcmanager-collect-method.md)|지정 된 세대에 대 한 가비지 수집을 강제로 수행 합니다.|  
|[GetStats 메서드](iclrgcmanager-getstats-method.md)|가비지 컬렉션 시스템에 대 한 현재 통계 집합을 가져옵니다.|  
|[SetGCStartupLimits 메서드](iclrgcmanager-setgcstartuplimits-method.md)|가비지 수집 세그먼트의 크기와 가비지 수집 시스템의 최대 0 세대 크기를 설정 합니다.|  
  
## <a name="remarks"></a>설명  

 CLR (공용 언어 런타임)은 관리 되는 형식을 사용 하 여 가비지 수집 메커니즘을 구현 합니다 <xref:System.GC> . 가비지 수집 시스템에 대 한 자세한 내용은 [가비지 수집](../../../standard/garbage-collection/index.md)을 참조 하세요.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [자동 메모리 관리](../../../standard/automatic-memory-management.md)
- [COR_GC_STATS 구조체](cor-gc-stats-structure.md)
- [ICLRControl 인터페이스](iclrcontrol-interface.md)
- [CLR 호스팅 인터페이스](clr-hosting-interfaces.md)
- [호스팅 인터페이스](hosting-interfaces.md)
- [호스팅](index.md)
