---
description: '다음에 대 한 자세한 정보: CorDebugPlatform 열거형'
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
ms.openlocfilehash: d6a78ec00f99ff34158f784e039372c8937e6d16
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661859"
---
# <a name="cordebugplatform-enumeration"></a>CorDebugPlatform 열거형

[ICorDebugDataTarget:: GetPlatform](icordebugdatatarget-getplatform-method.md) 메서드에서 사용 하는 대상 플랫폼 값을 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
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
  
## <a name="members"></a>구성원  
  
|멤버|설명|  
|------------|-----------------|  
|CORDB_PLATFORM_WINDOWS_X86|대상 플랫폼이 Intel x86 하드웨어에서 실행되는 Windows입니다.|  
|CORDB_PLATFORM_WINDOWS_AMD64|대상 플랫폼이 AMD64 또는 Intel EM64T 하드웨어에서 실행되는 64비트 Windows입니다.|  
|CORDB_PLATFORM_WINDOWS_IA64|대상 플랫폼이 Intel IA-64 하드웨어에서 실행되는 32비트 Windows입니다.|  
|CORDB_PLATFORM_MAC_PPC|대상 플랫폼은 PowerPC 하드웨어에서 실행 되는 Macintosh 운영 체제입니다.|  
|CORDB_PLATFORM_MAC_X86|대상 플랫폼은 Intel x86 하드웨어에서 실행 되는 Macintosh 운영 체제입니다.|  
|CORDB_PLATFORM_WINDOWS_ARM|대상 플랫폼은 Windows ARM 하드웨어에서 실행 되는 Macintosh 운영 체제입니다.|  
|CORDB_PLATFORM_MAC_AMD64|대상 플랫폼은 AMD64 하드웨어에서 실행 되는 Macintosh 운영 체제입니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
 `CORDB_PLATFORM_WINDOWS_ARM` 및 `CORDB_PLATFORM_MAC_AMD64` 멤버는 .NET Framework 4.5.2 이상 버전에서 사용 가능합니다.  
  
## <a name="see-also"></a>참고 항목

- [디버깅 열거형](debugging-enumerations.md)
