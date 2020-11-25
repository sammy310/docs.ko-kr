---
title: ICorConfiguration::SetGCThreadControl 메서드
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetGCThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCThreadControl
helpviewer_keywords:
- ICorConfiguration::SetGCThreadControl method [.NET Framework hosting]
- SetGCThreadControl method [.NET Framework hosting]
ms.assetid: 72e38e61-3d56-4ae3-b8f6-0ab7922aaf11
topic_type:
- apiref
ms.openlocfilehash: 28b012bbe3f8c11ecd0afb8b5905336bd99c349c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724028"
---
# <a name="icorconfigurationsetgcthreadcontrol-method"></a>ICorConfiguration::SetGCThreadControl 메서드

가비지 컬렉션에 대해 차단 되는 런타임 이외의 작업에 대해 스레드를 예약 하는 콜백 인터페이스를 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetGCThreadControl (  
    [in] IGCThreadControl* pGCThreadControl  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pGCThreadControl`  
 진행 런타임이 아닌 작업에 대 한 스레드 일시 중단을 호스트에 알리는 [Igcthreadcontrol](igcthreadcontrol-interface.md) 개체에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 호스트는 스레드를 다시 예약할 지 여부에 상관 없이 [Igcthreadcontrol:: ThreadIsBlockingForSuspension](igcthreadcontrol-threadisblockingforsuspension-method.md) 콜백 내에서 선택할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorConfiguration 인터페이스](icorconfiguration-interface.md)
