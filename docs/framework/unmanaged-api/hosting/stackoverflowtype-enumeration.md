---
description: '자세히 알아보기: StackOverflowType 열거형'
title: StackOverflowType 열거형
ms.date: 03/30/2017
api_name:
- StackOverflowType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StackOverflowType
helpviewer_keywords:
- StackOverflowType enumeration [.NET Framework hosting]
ms.assetid: dab648ad-972b-479c-b129-b4c1dcbd932e
topic_type:
- apiref
ms.openlocfilehash: d39ccd99331a3e839236f1ede21254edb92b2dfb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679357"
---
# <a name="stackoverflowtype-enumeration"></a>StackOverflowType 열거형

스택 오버플로 이벤트의 근본 원인을 나타내는 값을 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum {  
    SO_Managed,  
    SO_ClrEngine,  
    SO_Other  
} StackOverflowType;  
```  
  
## <a name="members"></a>구성원  
  
|멤버|설명|  
|------------|-----------------|  
|`SO_ClrEngine`|실행 엔진에서 스택 오버플로가 발생 했습니다.|  
|`SO_Managed`|관리 코드 때문에 스택 오버플로가 발생 했습니다.|  
|`SO_Other`|비관리 코드에서 스택 오버플로가 발생 했습니다.|  
  
## <a name="remarks"></a>설명  

 이 정보는 [IActionOnCLREvent:: OnEvent](iactiononclrevent-onevent-method.md) 메서드를 호출 하 여 호스트에 전달 됩니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [호스팅 열거형](hosting-enumerations.md)
