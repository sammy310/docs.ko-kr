---
title: MALLOC_TYPE 열거형
ms.date: 03/30/2017
api_name:
- MALLOC_TYPE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- MALLOC_TYPE
helpviewer_keywords:
- MALLOC_TYPE Enumeration
ms.assetid: c02476f9-23a2-4af7-9282-aa9c42c7429b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 695f69c8d9c3a295a705971743733339cf8aab13
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765221"
---
# <a name="malloctype-enumeration"></a>MALLOC_TYPE 열거형
할당 되는 메모리의 특징을 지정 하는 값을 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum {  
    MALLOC_THREADSAFE = 0x1,  
    MALLOC_EXECUTABLE = 0x2,  
} MALLOC_TYPE;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`MALLOC_EXECUTABLE`|할당된 된 메모리는 실행 파일을 포함할 수 있습니다.|  
|`MALLOC_THREADSAFE`|할당된 된 메모리는 스레드로부터 안전 합니다. 즉, 메모리 동기화 없이 여러 스레드에서 액세스할 수 있습니다.<br /><br /> 이 플래그를 설정 하지 않으면 개체에 대 한 호출이 serialize 되어야 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [호스팅 열거형](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
