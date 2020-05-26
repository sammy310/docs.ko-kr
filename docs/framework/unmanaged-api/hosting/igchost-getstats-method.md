---
title: IGCHost::GetStats 메서드
ms.date: 03/30/2017
api_name:
- IGCHost.GetStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetStats
helpviewer_keywords:
- GetStats method, IGCHost interface [.NET Framework hosting]
- IGCHost::GetStats method [.NET Framework hosting]
ms.assetid: c4ae022c-46ac-4f19-9ddd-09b955f19412
topic_type:
- apiref
ms.openlocfilehash: 67668aa7ff9faf035a047e485a8a3c8a451f45b9
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805244"
---
# <a name="igchostgetstats-method"></a>IGCHost::GetStats 메서드
가비지 수집 시스템의 현재 상태에 대 한 통계를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pStats`  
 [in, out] 가비지 수집 시스템의 현재 상태에 대 한 통계를 포함 하는 [COR_GC_STATS](cor-gc-stats-structure.md) 구조체에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 통계는 가비지 수집 시스템이 작동 하는 데 도움이 되는 스마트 할당 시스템에서 사용할 수 있습니다. 예를 들어 할당 시스템에서 통계를 검토 한 후 메모리를 더 추가 하거나 컬렉션을 강제 적용 해야 하는지 결정할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** GCHost, GCHost  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IGCHost 인터페이스](igchost-interface.md)
