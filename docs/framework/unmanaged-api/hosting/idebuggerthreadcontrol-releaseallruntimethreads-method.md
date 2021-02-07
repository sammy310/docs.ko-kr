---
description: '자세히 알아보기: IDebuggerThreadControl:: ReleaseAllRuntimeThreads 메서드'
title: IDebuggerThreadControl::ReleaseAllRuntimeThreads 메서드
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.ReleaseAllRuntimeThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ReleaseAllRuntimeThreads
helpviewer_keywords:
- ReleaseAllRuntimeThreads method [.NET Framework hosting]
- IDebuggerThreadControl::ReleaseAllRuntimeThreads method [.NET Framework hosting]
ms.assetid: 1a2995ff-5f02-4b49-84dc-3a5f9cfd7d55
topic_type:
- apiref
ms.openlocfilehash: bf551ccc2ae5bde3333dc8e3957099590a494dd3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709776"
---
# <a name="idebuggerthreadcontrolreleaseallruntimethreads-method"></a>IDebuggerThreadControl::ReleaseAllRuntimeThreads 메서드

디버깅 서비스가 차단 된 모든 스레드를 해제 하려고 한다는 사실을 호스트에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ReleaseAllRuntimeThreads ( );  
```  
  
## <a name="remarks"></a>설명  

 `ReleaseAllRuntimeThreads`메서드는 런타임 스레드에서 호출 되지 않습니다. 호스트에 차단 된 런타임 스레드가 있으면 지금 해제 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IDebuggerThreadControl 인터페이스](idebuggerthreadcontrol-interface.md)
