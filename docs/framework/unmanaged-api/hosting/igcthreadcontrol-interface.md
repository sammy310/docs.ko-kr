---
title: IGCThreadControl 인터페이스
ms.date: 03/30/2017
api_name:
- IGCThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCThreadControl
helpviewer_keywords:
- IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 3ff04d75-85ac-4df9-886d-dbaa037c0552
topic_type:
- apiref
ms.openlocfilehash: 3aba31f60af25144b9f01aa9ca8cc633d4c1a438
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134796"
---
# <a name="igcthreadcontrol-interface"></a>IGCThreadControl 인터페이스
가비지 컬렉션에 대해 차단 될 스레드의 예약에 참여 하기 위한 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[SuspensionEnding 메서드](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionending-method.md)|가비지 수집 또는 다른 일시 중단 후 런타임이 스레드를 다시 시작 하 고 있음을 호스트에 알립니다.|  
|[SuspensionStarting 메서드](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionstarting-method.md)|런타임에서 가비지 수집 또는 기타 일시 중단에 대 한 스레드 일시 중단을 시작 하 고 있음을 호스트에 알립니다.|  
|[ThreadIsBlockingForSuspension 메서드](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md)|호출 하는 스레드가 가비지 수집 또는 기타 일시 중단 등을 차단 하려고 함을 호스트에 알립니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
