---
title: IGCHost2::SetGCStartupLimitsEx 메서드
ms.date: 03/30/2017
api_name:
- IGCHost2.SetGCStartupLimitsEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost2::SetGCStartupLimitsEx
helpviewer_keywords:
- IGCHost2::SetGCStartupLimitsEx method [.NET Framework hosting]
- SetGCStartupLimitsEx method, IGCHost2 interface [.NET Framework hosting]
ms.assetid: bba941c2-1c57-46d3-bbf5-5fb92700c490
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da5e90055a08227ea7cb7fa1b459fe6f5f3a81fc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763219"
---
# <a name="igchost2setgcstartuplimitsex-method"></a>IGCHost2::SetGCStartupLimitsEx 메서드
0 세대에 대 한 세그먼트 크기 및 최대 크기를 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,  
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `SegmentSize`  
 [in] 가비지 컬렉션 시스템에서 사용 하는 세그먼트의 크기입니다.  
  
 `MaxGen0Size`  
 [in] 0 세대에 대 한 최대 크기입니다.  
  
## <a name="remarks"></a>설명  
 값을 `SetGCStartupLimitsEx` 집합 호스트 시작 되기 전에만 지정할 수 있습니다. 이러한 값은 나중에 변경할 수 없습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** GCHost.idl, GCHost.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [IGCHost2 인터페이스](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)
