---
description: IApartmentCallback::D oCallback 메서드에 대해 자세히 알아보세요.
title: IApartmentCallback::DoCallback 메서드
ms.date: 03/30/2017
api_name:
- IApartmentCallback.DoCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- DoCallback
helpviewer_keywords:
- IApartmentCallback::DoCallback method [.NET Framework hosting]
- DoCallback method [.NET Framework hosting]
ms.assetid: 8edad30c-30ff-4bee-813c-75525a82fc93
topic_type:
- apiref
ms.openlocfilehash: 65b7f496f953f08e099bf13ef8212c7d6e1026ff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785108"
---
# <a name="iapartmentcallbackdocallback-method"></a>IApartmentCallback::DoCallback 메서드

아파트 내에서 지정 된 함수를 실행 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT _stdcall DoCallback(  
    [in] SIZE_T pFunc,  
    [in] SIZE_T pData  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pFunc`  
 진행 아파트 내에서 실행 되는 함수에 대 한 포인터입니다.  
  
 `pData`  
 진행 함수 인수에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IApartmentCallback 인터페이스](iapartmentcallback-interface.md)
