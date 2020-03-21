---
title: ICLRGCManager2::SetGCStartupLimitsEx 메서드
ms.date: 03/30/2017
api_name:
- ICLRGCManager2.SetGCStartupLimitsEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager2::SetCLRGCStartupLimitsEx
helpviewer_keywords:
- ICLRGCManager2::SetGCStartupLimitsEx method [.NET Framework hosting]
- SetGCStartupLimitsEx method, ICLRGCManager2 interface [.NET Framework hosting]
ms.assetid: 6c3a08a9-5d65-48d4-8bbf-2a86ed7d356a
topic_type:
- apiref
ms.openlocfilehash: 9885149a71147db6eef13958b8ef825caa1d6ec6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176385"
---
# <a name="iclrgcmanager2setgcstartuplimitsex-method"></a>ICLRGCManager2::SetGCStartupLimitsEx 메서드
가비지 수집 세그먼트의 크기와 가비지 수집 시스템의 생성 0의 최대 크기를 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `SegmentSize`  
 【인】 가비지 수집 세그먼트의 지정된 크기입니다.  
  
 최소 세그먼트 크기는 4MB입니다. 세그먼트는 1MB 이상 단위로 늘릴 수 있습니다.  
  
 `MaxGen0Size`  
 【인】 0세대에 대해 지정된 최대 크기입니다.  
  
 최소 세대 0 크기는 64KB입니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|`SetGCStartupLimitsEx`성공적으로 반환됩니다.|  
|HOST_E_CLRNOTAVAILABLE|공통 언어 런타임(CLR)이 프로세스에 로드되지 않았거나 CLR이 관리 코드를 실행하거나 호출을 성공적으로 처리할 수 없는 상태입니다.|  
|HOST_E_TIMEOUT|통화 시간이 시간 미정으로 확인되었습니다.|  
|HOST_E_NOT_OWNER|호출자는 잠금을 소유하지 않습니다.|  
|HOST_E_ABANDONED|차단된 스레드 또는 파이버가 대기하는 동안 이벤트가 취소되었습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생했습니다. 메서드가 E_FAIL 반환하면 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다. 호스팅 메서드에 대한 후속 호출은 HOST_E_CLRNOTAVAILABLE 반환합니다.|  
  
## <a name="remarks"></a>설명  
 설정하는 `SetGCStartupLimitsEx` 값은 호스트가 시작되기 전에만 지정할 수 있습니다. 나중에 `SetGCStartupLimitsEx` 호출은 무시됩니다.  
  
 다른 매개 변수에 영향을 주지 않고 두 매개 변수를 설정하려면 변경하지 않으려는 매개 변수에 대해 0(0)을 지정합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MSCorE.h  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [자동 메모리 관리](../../../standard/automatic-memory-management.md)
- [가비지 수집](../../../standard/garbage-collection/index.md)
- [ICLRControl 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [ICLRGCManager2 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)
