---
title: StackOverflowInfo 구조체
ms.date: 03/30/2017
api_name:
- StackOverflowInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StackOverflowInfo
helpviewer_keywords:
- StackOverflowInfo structure [.NET Framework hosting]
ms.assetid: 519389f2-0217-436c-99d4-93a76ebce5b5
topic_type:
- apiref
ms.openlocfilehash: a8a57cfcaf36949d4d10c6ec267a5f55a2aee5eb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729930"
---
# <a name="stackoverflowinfo-structure"></a>StackOverflowInfo 구조체

발생 한 오버플로 형식과 오버플로로 인해 throw 된 예외에 대 한 정보를 저장 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct _StackOverflowInfo {  
    StackOverflowType   soType;  
    EXCEPTION_POINTERS  *pExceptionInfo;  
} StackOverflowInfo;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`soType`|오버플로 유형을 지정 하는 [StackOverflowType](stackoverflowtype-enumeration.md) 열거형의 값입니다.|  
|`pExceptionInfo`|예외에 대 한 컴퓨터 독립적 설명과 컨텍스트 레코드를 포함 하는 예외 레코드를 포함 하는 Win32 개체에 대 한 포인터로 `EXCEPTION_POINTERS` , 예외 발생 시 프로세서 컨텍스트에 대 한 컴퓨터 종속 설명을 포함 합니다.|  
  
## <a name="remarks"></a>설명  

 `StackOverflowInfo`개체는 이벤트에 대 한 [IActionOnCLREvent:: OnEvent](iactiononclrevent-onevent-method.md) 메서드에 전달 됩니다 `Event_StackOverflow` .  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [호스팅 구조체](hosting-structures.md)
