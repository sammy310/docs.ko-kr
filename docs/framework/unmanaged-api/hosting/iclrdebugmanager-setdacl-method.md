---
description: '자세히 알아보기: ICLRDebugManager:: SetDacl 메서드'
title: ICLRDebugManager::SetDacl 메서드
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.SetDacl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::SetDacl
helpviewer_keywords:
- SetDacl method [.NET Framework hosting]
- ICLRDebugManager::SetDacl method [.NET Framework hosting]
ms.assetid: 52f4af3f-e02b-4c20-9fd9-e8e4f4d6fc31
topic_type:
- apiref
ms.openlocfilehash: b507d94f9e23e509d279a0fd4e32c8c996a4668b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689575"
---
# <a name="iclrdebugmanagersetdacl-method"></a>ICLRDebugManager::SetDacl 메서드

이 메서드가 구현되지 않은 경우  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetDacl (  
    [in] PACL pacl  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pacl`  
 진행 ACL (Access Control 목록)에 대 한 포인터입니다.  
  
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
- [GetDacl 메서드](iclrdebugmanager-getdacl-method.md)
- [IHostControl 인터페이스](ihostcontrol-interface.md)
