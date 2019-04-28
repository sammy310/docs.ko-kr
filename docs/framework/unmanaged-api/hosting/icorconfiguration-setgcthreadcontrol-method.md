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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b50c87efeb8ad2311a75886da677a9dc901bca1b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763232"
---
# <a name="icorconfigurationsetgcthreadcontrol-method"></a>ICorConfiguration::SetGCThreadControl 메서드
가비지 컬렉션에 대해 차단 될 수 있는 런타임 이외의 작업에 대 한 스레드를 예약 하는 것에 대 한 콜백 인터페이스를 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetGCThreadControl (  
    [in] IGCThreadControl* pGCThreadControl  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pGCThreadControl`  
 [in] 에 대 한 포인터를 [IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md) 개체는 런타임 이외의 작업에 대 한 스레드의 일시 중단 하는 방법에 대 한 호스트에 알립니다.  
  
## <a name="remarks"></a>설명  
 호스트 내에서 선택할 수는 [igcthreadcontrol:: Threadisblockingforsuspension](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md) 콜백 스레드를 예약 하기 위한 여부.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [ICorConfiguration 인터페이스](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
