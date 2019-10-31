---
title: BucketParameters 구조체
ms.date: 03/30/2017
api_name:
- BucketParameters
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- BucketParameters
helpviewer_keywords:
- BucketParameters structure [.NET Framework hosting]
ms.assetid: 9432487e-f276-45d6-9a13-9a68024dbd46
topic_type:
- apiref
ms.openlocfilehash: 80623bdec939b0ae5fc13008c1c4001c613ac435
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195954"
---
# <a name="bucketparameters-structure"></a>BucketParameters 구조체
이벤트의 형식 이름 및 이벤트와 연결 된 현재 예외에 대 한 매개 변수를 저장 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct _BucketParameters {  
    BOOL  fInited;                    
    WCHAR pszEventTypeName[255];      
    WCHAR pszParams[10][255];         
} BucketParameters;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`fInited`|이 구조체의 나머지가 유효한 경우 `true`합니다. 그렇지 않으면 `false`합니다.|  
|`pszEventTypeName`|이벤트 유형의 이름입니다.|  
|`pszParams`|각각 이벤트와 연결 된 현재 예외에 대 한 매개 변수를 지정 하는 문자열의 배열입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [호스팅 구조체](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
