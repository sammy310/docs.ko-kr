---
title: WAITORTIMERCALLBACK 함수 포인터
ms.date: 03/30/2017
api_name:
- WAITORTIMERCALLBACK
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- WAITORTIMERCALLBACK
helpviewer_keywords:
- WAITORTIMERCALLBACK function pointer [.NET Framework hosting]
ms.assetid: 1fec4aef-0a06-4df0-bae7-d31a9ef9603d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 24a2c3baec0d958302101c295966f945ae98fa78
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57490712"
---
# <a name="waitortimercallback-function-pointer"></a>WAITORTIMERCALLBACK 함수 포인터
호스트는 대기 핸들에 알리는 함수를 가리키는 (<xref:System.Threading.WaitHandle>) 하거나 신호가 전달 되거나 시간이 초과 되었습니다.  
  
 이 함수 포인터에서 사용 중단에 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef VOID (__stdcall *WAITORTIMERCALLBACK) (  
    [in] PVOID lpParameter,  
    [in] BOOL  TimerOrWaitFired  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `lpParameter`  
 [in] 호스트에 의해 정의 된 정보를 포함 하는 개체에 대 한 포인터입니다.  
  
 `TimerOrWaitFired`  
 [in] `true` 대기 핸들을 초과 하는 경우 또는 `false` 된 신호를 받은 경우.  
  
## <a name="remarks"></a>설명  
 함수는 `WAITORTIMERCALLBACK` 지점은 콜백 함수 및 호스팅 응용 프로그램의 작성기에 의해 구현 되어야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorWks.dll  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료
- [사용되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
