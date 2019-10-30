---
title: HOST_TYPE 열거형
ms.date: 03/30/2017
api_name:
- HOST_TYPE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- HOST_TYPE
helpviewer_keywords:
- HOST_TYPE enumeration [.NET Framework hosting]
ms.assetid: 51f848be-84c5-4036-9839-c762c576bbf5
topic_type:
- apiref
ms.openlocfilehash: cc0cea10b4a209583fb7afb551a6b80d52ad7f62
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127024"
---
# <a name="host_type-enumeration"></a>HOST_TYPE 열거형
응용 프로그램을 시작 하는 호스트의 유형을 지정 하는 값을 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|AppLaunch에서 응용 프로그램을 시작 합니다.<br /><br /> 부분적으로 신뢰할 수 있는 응용 프로그램에이 값을 사용 합니다.|  
|`HOST_TYPE_CORFLAG`|응용 프로그램을 직접 시작 합니다. 즉, 자체 .exe 파일에서 응용 프로그램을 시작 합니다.<br /><br /> 완전히 신뢰할 수 있는 응용 프로그램에이 값을 사용 합니다.|  
|`HOST_TYPE_DEFAULT`|HOST_TYPE_APPLAUNCH와 동일 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [호스팅 열거형](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
