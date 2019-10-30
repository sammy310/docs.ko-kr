---
title: IGCHost::Collect 메서드
ms.date: 03/30/2017
api_name:
- IGCHost.Collect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Collect
helpviewer_keywords:
- Collect method, IGCHost interface [.NET Framework hosting]
- IGCHost::Collect method [.NET Framework hosting]
ms.assetid: fc7d9448-3186-494d-9f0d-ea39717e9a82
topic_type:
- apiref
ms.openlocfilehash: e20ea6addc1ae3f99b4b3d65f532e0128ac160b3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134966"
---
# <a name="igchostcollect-method"></a>IGCHost::Collect 메서드
현재 가비지 컬렉션의 상태에 관계 없이 지정 된 세대에 대해 컬렉션을 강제로 실행 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `Generation`  
 진행 가비지 수집을 수행할 세대입니다. 값-1은 모든 세대에서 가비지 수집을 수행 함을 나타냅니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** GCHost, GCHost  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [IGCHost 인터페이스](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
