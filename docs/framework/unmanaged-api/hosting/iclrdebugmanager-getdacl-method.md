---
description: '자세히 알아보기: ICLRDebugManager:: GetDacl 메서드'
title: ICLRDebugManager::GetDacl 메서드
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.GetDacl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::GetDacl
helpviewer_keywords:
- GetDacl method [.NET Framework hosting]
- ICLRDebugManager::GetDacl method [.NET Framework hosting]
ms.assetid: 7115e920-aaff-440a-824e-39497139c6f6
topic_type:
- apiref
ms.openlocfilehash: 8a1b747851d0c5104dbe18e5a66742d57b09aa22
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649483"
---
# <a name="iclrdebugmanagergetdacl-method"></a>ICLRDebugManager::GetDacl 메서드

이 메서드가 구현되지 않은 경우  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetDacl (  
    [out] PACL* ppacl  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `ppacl`  
 제한이 ACL (Access Control 목록)에 대 한 인터페이스 포인터입니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|설명|  
|-------------|-----------------|  
|E_NOTIMPL|메서드가 구현되지 않았습니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRControl 인터페이스](iclrcontrol-interface.md)
- [ICLRDebugManager 인터페이스](iclrdebugmanager-interface.md)
- [SetDacl 메서드](iclrdebugmanager-setdacl-method.md)
- [IHostControl 인터페이스](ihostcontrol-interface.md)
