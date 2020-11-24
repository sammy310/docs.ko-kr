---
title: ICLRGCManager2 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRGCManager2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager2
helpviewer_keywords:
- ICLRGCManager2 interface [.NET Framework hosting]
ms.assetid: 4b5ffd7b-9ad7-41cd-9bba-34030ae3da7e
topic_type:
- apiref
ms.openlocfilehash: d2873b5e1f8229e8a16dfaacf1c9737ac47405bb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672801"
---
# <a name="iclrgcmanager2-interface"></a>ICLRGCManager2 인터페이스

호스트가 공용 언어 런타임의 가비지 수집 시스템과 상호 작용할 수 있도록 하는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[SetGCStartupLimitsEx 메서드](iclrgcmanager2-setgcstartuplimitsex-method.md)|가비지 수집 세그먼트의 크기와 가비지 수집 시스템의 최대 0 세대 크기를 설정 합니다. 0 세대 및 세그먼트 크기를 보다 크게 설정 `DWORD` 합니다.|  
  
## <a name="remarks"></a>설명  

 이 인터페이스는 [ICLRGCManager 인터페이스](iclrgcmanager-interface.md)에서 상속 됩니다.  
  
 CLR (공용 언어 런타임)은 관리 되는 형식을 사용 하 여 가비지 수집 메커니즘을 구현 합니다 <xref:System.GC> . 가비지 수집 시스템에 대 한 자세한 내용은 [가비지 수집](../../../standard/garbage-collection/index.md)을 참조 하세요.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참조

- [자동 메모리 관리](../../../standard/automatic-memory-management.md)
- [COR_GC_STATS 구조체](cor-gc-stats-structure.md)
- [ICLRControl 인터페이스](iclrcontrol-interface.md)
- [.NET Framework 4 및 4.5에 추가된 CLR 호스팅 인터페이스](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [호스팅 인터페이스](hosting-interfaces.md)
- [호스팅](index.md)
