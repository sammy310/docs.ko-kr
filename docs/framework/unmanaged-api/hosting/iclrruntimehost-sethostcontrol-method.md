---
title: ICLRRuntimeHost::SetHostControl 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.SetHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::SetHostControl
helpviewer_keywords:
- SetHostControl method [.NET Framework hosting]
- ICLRRuntimeHost::SetHostControl method [.NET Framework hosting]
ms.assetid: 6136be87-e631-4756-81ed-74b66581bad4
topic_type:
- apiref
ms.openlocfilehash: 32483be43d4d4fe9d185c091e15a13c6feb95600
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728825"
---
# <a name="iclrruntimehostsethostcontrol-method"></a>ICLRRuntimeHost::SetHostControl 메서드

CLR (공용 언어 런타임)에서 호스트의 [IHostControl 인터페이스](ihostcontrol-interface.md)구현을 가져오는 데 사용할 수 있는 인터페이스 포인터를 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetHostControl(  
    [in] IHostControl* pHostControl  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pHostControl`  
 진행 호스트의 [IHostControl 인터페이스](ihostcontrol-interface.md)구현에 대 한 인터페이스 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`SetHostControl` 성공적으로 반환 되었습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
|E_CLR_ALREADY_STARTED|CLR이 이미 초기화 되었습니다.|  
  
## <a name="remarks"></a>설명  

 CLR을 초기화 하기 전에를 호출 해야 합니다 `SetHostControl` . 즉, [시작 메서드](iclrruntimehost-start-method.md) 를 호출 하거나 [메타 데이터 인터페이스](../metadata/metadata-interfaces.md)를 사용 하기 전에를 호출 해야 합니다. `SetHostControl` [CorBindToCurrentRuntime 함수](corbindtocurrentruntime-function.md) 또는 [CorBindToRuntimeEx 함수](corbindtoruntimeex-function.md)를 호출한 후 즉시 호출 하는 것이 좋습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRRuntimeHost 인터페이스](iclrruntimehost-interface.md)
- [IHostControl 인터페이스](ihostcontrol-interface.md)
