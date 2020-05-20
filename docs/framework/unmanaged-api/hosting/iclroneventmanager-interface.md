---
title: ICLROnEventManager 인터페이스
ms.date: 03/30/2017
api_name:
- ICLROnEventManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager
helpviewer_keywords:
- ICLROnEventManager interface [.NET Framework hosting]
ms.assetid: 9e15a0c1-8ab6-43d0-ae28-6ec7a4edd913
topic_type:
- apiref
ms.openlocfilehash: 30312e6e09535cee2968b1f9e8ac87b461c5ff40
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703513"
---
# <a name="iclroneventmanager-interface"></a>ICLROnEventManager 인터페이스
호스트가 CLR (공용 언어 런타임) 이벤트에 대 한 콜백을 등록 하 고 등록 취소할 수 있도록 하는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[RegisterActionOnEvent 메서드](iclroneventmanager-registeractiononevent-method.md)|지정 된 이벤트에 대 한 콜백 포인터를 등록 합니다.|  
|[UnregisterActionOnEvent 메서드](iclroneventmanager-unregisteractiononevent-method.md)|지정 된 이벤트에 대해 이전에 등록 된 콜백 포인터의 등록을 취소 합니다.|  
  
## <a name="remarks"></a>설명  
 이벤트 콜백을 등록 하 고 등록을 취소 하기 위해 호스트는 `ICLROnEventManager` [ICLRControl:: GetCLRManager](iclrcontrol-getclrmanager-method.md) 메서드를 호출 하 여에 대 한 참조를 가져옵니다.  
  
> [!NOTE]
> [EClrEvent](eclrevent-enumeration.md) 에서 설명 하는 이벤트는 여러 스레드에서 두 번 이상 발생 하 여 언로드 또는 CLR 비활성화를 알릴 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [EClrEvent 열거형](eclrevent-enumeration.md)
- [IActionOnCLREvent 인터페이스](iactiononclrevent-interface.md)
- [ICLRControl 인터페이스](iclrcontrol-interface.md)
- [호스팅 인터페이스](hosting-interfaces.md)
