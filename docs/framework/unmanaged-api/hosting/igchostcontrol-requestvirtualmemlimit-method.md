---
title: IGCHostControl::RequestVirtualMemLimit 메서드
ms.date: 03/30/2017
api_name:
- IGCHostControl.RequestVirtualMemLimit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- RequestVirtualMemLimit
helpviewer_keywords:
- IGCHostControl::RequestVirtualMemLimit method [.NET Framework hosting]
- RequestVirtualMemLimit method [.NET Framework hosting]
ms.assetid: f4984a8c-4c0e-4460-9aa1-d022b3621228
topic_type:
- apiref
ms.openlocfilehash: bbcabdec45945b969230a40b85a62e24e323ccc4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733934"
---
# <a name="igchostcontrolrequestvirtualmemlimit-method"></a>IGCHostControl::RequestVirtualMemLimit 메서드

가상 메모리의 한도를 변경 하도록 호스트에 요청 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT RequestVirtualMemLimit (  
    [in] SIZE_T       sztMaxVirtualMemMB,  
    [in, out] SIZE_T* psztNewMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `sztMaxVirtualMemMB`  
 진행 할당 될 요청 된 메모리 크기입니다.  
  
 `psztNewMaxVirtualMemMB`  
 [in, out] 할당 된 메모리의 실제 크기에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [IGCHostControl 인터페이스](igchostcontrol-interface.md)
