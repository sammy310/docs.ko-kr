---
description: '자세히 알아보기: ICLROnEventManager:: RegisterActionOnEvent 메서드'
title: ICLROnEventManager::RegisterActionOnEvent 메서드
ms.date: 03/30/2017
api_name:
- ICLROnEventManager.RegisterActionOnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager::RegisterActionOnEvent
helpviewer_keywords:
- ICLROnEventManager::RegisterActionOnEvent method [.NET Framework hosting]
- RegisterActionOnEvent method [.NET Framework hosting]
ms.assetid: b944cf49-918d-4c4e-993b-77d097a52550
topic_type:
- apiref
ms.openlocfilehash: b13209aed6a169185b42c6b9520f21f59f6be3bb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637432"
---
# <a name="iclroneventmanagerregisteractiononevent-method"></a>ICLROnEventManager::RegisterActionOnEvent 메서드

지정 된 이벤트에 대 한 콜백 포인터를 등록 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT RegisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `event`  
 진행 에 설명 된 콜백 포인터를 등록할 이벤트를 나타내는 [EClrEvent](eclrevent-enumeration.md) 값 중 하나 `pAction` 입니다.  
  
 `pAction`  
 진행 등록 된 이벤트가 발생할 때 호출 되는 [IActionOnCLREvent](iactiononclrevent-interface.md) 개체에 대 한 포인터입니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`RegisterActionOnEvent` 성공적으로 반환 되었습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
  
## <a name="remarks"></a>설명  

 호스트는에서 설명 하는 두 이벤트 형식 중 하나 또는 둘 다에 대해 콜백을 등록할 수 있습니다 `EClrEvent` . 호스트는 `ICLROnEventManager` [ICLRControl:: GetCLRManager](iclrcontrol-getclrmanager-method.md) 메서드를 호출 하 여 인터페이스를 가져옵니다.  
  
> [!NOTE]
> 를 등록 하는 이벤트는 `RegisterActionOnEvent` 여러 스레드에서 두 번 이상 발생 하 여 언로드 또는 CLR 비활성화를 알릴 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [EClrEvent 열거형](eclrevent-enumeration.md)
- [IActionOnCLREvent 인터페이스](iactiononclrevent-interface.md)
- [ICLRControl 인터페이스](iclrcontrol-interface.md)
- [ICLROnEventManager 인터페이스](iclroneventmanager-interface.md)
