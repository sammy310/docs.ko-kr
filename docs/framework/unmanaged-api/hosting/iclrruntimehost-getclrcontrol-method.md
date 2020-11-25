---
title: ICLRRuntimeHost::GetCLRControl 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.GetCLRControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::GetCLRControl
helpviewer_keywords:
- ICLRRuntimeHost::GetCLRControl method [.NET Framework hosting]
- GetCLRControl method [.NET Framework hosting]
ms.assetid: e47e3655-efd5-4572-a1dc-50c69bf2a468
topic_type:
- apiref
ms.openlocfilehash: 928ac05fbd3a19a17e7f37674b2a75f8bc799fc6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728876"
---
# <a name="iclrruntimehostgetclrcontrol-method"></a>ICLRRuntimeHost::GetCLRControl 메서드

에서 CLR (공용 언어 런타임)의 측면을 사용자 지정 하는 데 사용할 수 있는 [ICLRControl interface](iclrcontrol-interface.md) 형식의 인터페이스 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetCLRControl(  
    [out] ICLRControl** pCLRControl  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pCLRControl`  
 제한이 호스트가 CLR의 추가 측면을 구성할 수 있도록 하는 [ICLRControl interface](iclrcontrol-interface.md) 형식의 인터페이스 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`GetCLRControl` 성공적으로 반환 되었습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
|HOST_E_INVALIDOPERATION|CLR이 이미 시작 되었습니다.|  
  
## <a name="remarks"></a>설명  

 `ICLRControl` 호스트에서 관리자 형식 중 하나에 대 한 인터페이스 포인터를 가져올 수 있도록 하는 [Getclrmanager 메서드](iclrcontrol-getclrmanager-method.md) 메서드를 제공 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRControl 인터페이스](iclrcontrol-interface.md)
- [ICLRRuntimeHost 인터페이스](iclrruntimehost-interface.md)
