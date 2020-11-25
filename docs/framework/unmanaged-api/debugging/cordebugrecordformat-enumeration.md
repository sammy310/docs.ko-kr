---
title: CorDebugRecordFormat 열거형
ms.date: 03/30/2017
api_name:
- CorDebugRecordFormat
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: d680c1c0-16ab-4ccc-9444-39cf8e0e05ee
topic_type:
- apiref
ms.openlocfilehash: b3a22d7b32eb258263d373ae91b3fb7fbc9aae99
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696390"
---
# <a name="cordebugrecordformat-enumeration"></a>CorDebugRecordFormat 열거형

네이티브 예외 디버그 이벤트에 대한 정보가 포함된 바이트 배열의 데이터 형식을 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum CorDebugRecordFormat {  
    FORMAT_WINDOWS_EXCEPTIONRECORD32 = 1,  
    FORMAT_WINDOWS_EXCEPTIONRECORD64 = 2,  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD32`|데이터가 32비트 Windows 예외 레코드입니다.|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD64`|데이터가 64비트 Windows 예외 레코드입니다.|  
  
## <a name="remarks"></a>설명  

 열거형의 멤버는 `CorDebugRecordFormat` 인수에서 바이트 배열의 형식을 나타내기 위해 [DecodeEvent](icordebugprocess6-decodeevent-method.md) 메서드에 전달 됩니다 `pRecord` .  
  
> [!NOTE]
> 이 열거형은 .NET 네이티브 디버깅 시나리오에서만 사용됩니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 열거형](debugging-enumerations.md)
