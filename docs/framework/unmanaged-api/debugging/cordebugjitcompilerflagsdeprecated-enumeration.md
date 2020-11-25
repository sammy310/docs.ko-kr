---
title: CorDebugJITCompilerFlagsDeprecated 열거형
ms.date: 03/30/2017
api_name:
- CorDebugJITCompilerFlagsDeprecated
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugJITCompilerFlagsDeprecated
helpviewer_keywords:
- CorDebugJITCompilerFlagsDeprecated enumeration [.NET Framework debugging]
ms.assetid: af15e2ca-6be1-472b-bd36-03644a1e3ddd
topic_type:
- apiref
ms.openlocfilehash: 8797f77388bf4992dfb69191ce8a844a9b7fdb8a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696442"
---
# <a name="cordebugjitcompilerflagsdeprecated-enumeration"></a>CorDebugJITCompilerFlagsDeprecated 열거형

이 열거형은 사용 되지 않습니다. `CORDEBUG_JIT_DEFAULT`대신 [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) 열거형의 멤버를 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum CorDebugJITCompilerFlagsDeprecated {  
    CORDEBUG_JIT_TRACK_DEBUG_INFO  = 0x1  
} CorDebugJITCompilerFlagsDeprecated;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`CORDEBUG_JIT_TRACK_DEBUG_INFO`|대신 `CORDEBUG_JIT_DEFAULT`를 사용하세요.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** 1.0, 1.1  
  
## <a name="see-also"></a>참조

- [디버깅 열거형](debugging-enumerations.md)
