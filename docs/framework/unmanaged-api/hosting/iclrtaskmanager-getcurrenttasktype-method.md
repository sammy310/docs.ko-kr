---
title: ICLRTaskManager::GetCurrentTaskType 메서드
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.GetCurrentTaskType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::GetCurrentTaskType
helpviewer_keywords:
- GetCurrentTaskType method [.NET Framework hosting]
- ICLRTaskManager::GetCurrentTaskType method [.NET Framework hosting]
ms.assetid: 6b0d9259-dbe2-45bb-b34d-990f60c73424
topic_type:
- apiref
ms.openlocfilehash: 684b94471c53701c5ebe1dc7e7593eae16ad50fd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728786"
---
# <a name="iclrtaskmanagergetcurrenttasktype-method"></a>ICLRTaskManager::GetCurrentTaskType 메서드

현재 실행 중인 작업의 형식을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetCurrentTaskType(  
    [out] ETaskType *pTaskType  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pTaskType`  
 제한이 현재 실행 중인 작업의 유형을 나타내는 [Etasktype](etasktype-enumeration.md) 열거형의 값에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRTaskManager 인터페이스](iclrtaskmanager-interface.md)
