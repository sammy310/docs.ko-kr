---
title: VariableLocationType 열거형
ms.date: 03/30/2017
api_name:
- VariableLocationType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- VariableLocationType
helpviewer_keywords:
- VariableLocationType enumeration [.NET Framework debugging]
ms.assetid: 8635ee3a-c84b-4626-876c-416bee54f787
topic_type:
- apiref
ms.openlocfilehash: 1c65efa006a8b2f4fb4db257b4ad2cde99c4e75e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725263"
---
# <a name="variablelocationtype-enumeration"></a>VariableLocationType 열거형

변수의 기본 위치 유형을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,
    VLT_REGISTER_RELATIVE,
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`VLT_REGISTER`|변수가 레지스터에 있습니다.|  
|`VLT_REGISTER_RELATIVE`|변수가 등록 관련 메모리 위치에 있습니다.|  
|`VLT_INVALID`|변수는 레지스터 또는 등록 관련 메모리 위치에 저장 되지 않습니다.|  
  
## <a name="remarks"></a>설명  

 열거형의 멤버는 `VariableLocationType` [ICorDebugVariableHome:: GetLocationType](icordebugvariablehome-getlocationtype-method.md) 메서드에서 반환 됩니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 열거형](debugging-enumerations.md)
