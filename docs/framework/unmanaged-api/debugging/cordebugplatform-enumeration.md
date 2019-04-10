---
title: CorDebugPlatform 열거형
ms.date: 03/30/2017
api_name:
- CorDebugPlatformEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugPlatformEnum
helpviewer_keywords:
- CorDebugPlatformEnum enumeration [.NET Framework debugging]
ms.assetid: c5444816-7378-4521-afd3-bf5e4b5303d5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03b6f1b29157889d0e84e5dddc94d5e3ae27efce
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59180943"
---
# <a name="cordebugplatform-enumeration"></a>CorDebugPlatform 열거형
사용 되는 대상 플랫폼 값을 제공 합니다 [icordebugdatatarget:: Getplatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) 메서드.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum CorDebugPlatform  
{  
    CORDB_PLATFORM_WINDOWS_X86,    // Windows on Intel x86  
    CORDB_PLATFORM_WINDOWS_AMD64,  // Windows x64 (AMD64, Intel EM64T)  
    CORDB_PLATFORM_WINDOWS_IA64,   // Windows on Intel IA-64  
    CORDB_PLATFORM_MAC_PPC,        // Macintosh OS on PowerPC  
    CORDB_PLATFORM_MAC_X86,        // Macintosh OS on Intel x86  
    CORDB_PLATFORM_WINDOWS_ARM,    // Windows on ARM  
    CORDB_PLATFORM_MAC_AMD64       // MacOS on Intel x64  
} CorDebugPlatform;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|CORDB_PLATFORM_WINDOWS_X86|대상 플랫폼이 Intel x86 하드웨어에서 실행되는 Windows입니다.|  
|CORDB_PLATFORM_WINDOWS_AMD64|대상 플랫폼이 AMD64 또는 Intel EM64T 하드웨어에서 실행되는 64비트 Windows입니다.|  
|CORDB_PLATFORM_WINDOWS_IA64|대상 플랫폼이 Intel IA-64 하드웨어에서 실행되는 32비트 Windows입니다.|  
|CORDB_PLATFORM_MAC_PPC|대상 플랫폼이 PowerPC 하드웨어에서 실행 되는 Macintosh 운영 체제는입니다.|  
|CORDB_PLATFORM_MAC_X86|대상 플랫폼이 Intel x86 하드웨어에서 실행 하는 Macintosh 운영 체제는입니다.|  
|CORDB_PLATFORM_WINDOWS_ARM|대상 플랫폼이 Windows ARM 하드웨어에서 실행 되는 Macintosh 운영 체제는입니다.|  
|CORDB_PLATFORM_MAC_AMD64|대상 플랫폼이 AMD64 하드웨어에서 실행 되는 Macintosh 운영 체제는입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
 `CORDB_PLATFORM_WINDOWS_ARM` 및 `CORDB_PLATFORM_MAC_AMD64` 멤버는 .NET Framework 4.5.2 이상 버전에서 사용 가능합니다.  
  
## <a name="see-also"></a>참고자료

- [디버깅 열거형](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
