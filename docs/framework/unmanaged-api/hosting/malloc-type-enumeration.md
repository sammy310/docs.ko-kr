---
description: '다음에 대 한 자세한 정보: 열거형 MALLOC_TYPE'
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
ms.openlocfilehash: 47eb58107d79309c34af5f0acdf614804d1f208f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679804"
---
# <a name="malloc_type-enumeration"></a>MALLOC_TYPE 열거형

할당 되는 메모리의 특성을 지정 하는 값을 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum {  
    MALLOC_THREADSAFE = 0x1,  
    MALLOC_EXECUTABLE = 0x2,  
} MALLOC_TYPE;  
```  
  
## <a name="members"></a>구성원  
  
|멤버|설명|  
|------------|-----------------|  
|`MALLOC_EXECUTABLE`|할당 된 메모리는 실행 파일을 포함할 수 있습니다.|  
|`MALLOC_THREADSAFE`|할당 된 메모리는 스레드로부터 안전 합니다. 즉, 동기화 하지 않고 여러 스레드를 사용 하 여 메모리에 액세스할 수 있습니다.<br /><br /> 이 플래그를 설정 하지 않으면 개체에 대 한 호출을 직렬화 해야 합니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [호스팅 열거형](hosting-enumerations.md)
